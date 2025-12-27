Below is a **complete, structured guide to Java Security Providers** — what they are, **all common providers you’ll see**, what each one does, and **how to inspect every detail programmatically**.

This is written as a **reference-style answer** you can keep for interviews, audits, or real projects.

---

# 1. What “All Provider Details” Means in Java

For each provider, Java defines:

* **Name** (e.g., `SunJCE`)
* **Version**
* **Vendor**
* **Services provided**

  * Algorithms (AES, RSA, SHA-256)
  * Modes (GCM, CBC)
  * Padding (PKCS5Padding)
  * KeyStores, Signatures, MACs, etc.

---

# 2. Default Providers in OpenJDK / Oracle JDK

Run this to confirm on your system:

```java
import java.security.Security;

public class ListProviders {
    public static void main(String[] args) {
        for (var provider : Security.getProviders()) {
            System.out.println(provider.getName() + " - " +
                               provider.getVersionStr() + " - " +
                               provider.getInfo());
        }
    }
}
```

---

## 2.1 Typical Default Providers (Java 8–21)

| Order | Provider       | Purpose                          |
| ----- | -------------- | -------------------------------- |
| 1     | **SUN**        | Core security, SHA, SecureRandom |
| 2     | **SunRsaSign** | RSA signatures                   |
| 3     | **SunEC**      | Elliptic Curve crypto            |
| 4     | **SunJSSE**    | TLS/SSL                          |
| 5     | **SunJCE**     | Symmetric crypto (AES, DES)      |
| 6     | **SunJGSS**    | Kerberos                         |
| 7     | **SunSASL**    | SASL                             |
| 8     | **XMLDSig**    | XML Digital Signatures           |
| 9     | **SunPCSC**    | Smart cards                      |
| 10    | **JdkLDAP**    | LDAP                             |
| 11    | **JdkSASL**    | SASL                             |
| 12    | **SunPKCS11**  | PKCS#11 (HSMs, smart cards)      |

---

# 3. What Each Provider Supports (Key Highlights)

---

## 3.1 SUN Provider

🔹 Low-level primitives
🔹 **No encryption**

Supports:

* `MessageDigest` (SHA-1, SHA-256)
* `SecureRandom`
* `CertificateFactory`

---

## 3.2 SunJCE (Most Important One)

🔹 Main **encryption provider**

Supports:

* AES, DES, DESede
* Modes: ECB, CBC, CFB, OFB, CTR, GCM
* Padding: PKCS5Padding, NoPadding

❌ Does NOT support:

* AES-XTS
* ISO7816Padding
* ZeroPadding

---

## 3.3 SunEC

🔹 Elliptic Curve crypto

Supports:

* ECDSA
* ECDH
* Curves: secp256r1, secp384r1

---

## 3.4 SunRsaSign

🔹 RSA signatures only

Supports:

* SHA256withRSA
* SHA512withRSA

---

## 3.5 SunJSSE

🔹 TLS provider

Supports:

* HTTPS
* TLS 1.2 / 1.3
* KeyManagers, TrustManagers

---

## 3.6 SunPKCS11

🔹 Bridge to **hardware / HSM**

Supports:

* Whatever the hardware supports
* FIPS enforcement possible

---

# 4. Third-Party Providers (Common)

---

## 4.1 Bouncy Castle (BC)

🔹 Most feature-rich provider

Supports:

* AES-XTS
* ISO7816-4 Padding
* ZeroPadding
* ChaCha20
* Post-quantum crypto

Not enabled by default.

---

## 4.2 Bouncy Castle FIPS (BCFIPS)

🔹 FIPS 140-2 / 140-3 compliant

* Enforces strict crypto rules
* Disables DES, ECB
* Used in regulated industries

---

## 4.3 Conscrypt (Google)

🔹 High-performance TLS + crypto

* Used in Android
* Fast AES/GCM

---

# 5. How to List **ALL Algorithms** per Provider

### Full Algorithm Dump Code

```java
import java.security.Provider;
import java.security.Security;
import java.util.Set;
import java.util.TreeSet;

public class ProviderDetails {

    public static void main(String[] args) {
        for (Provider provider : Security.getProviders()) {
            System.out.println("\nProvider: " + provider.getName());
            Set<String> services = new TreeSet<>();

            for (Provider.Service service : provider.getServices()) {
                services.add(service.getType() + " : " + service.getAlgorithm());
            }

            services.forEach(System.out::println);
        }
    }
}
```

This prints:

* Cipher algorithms
* Message digests
* MACs
* Signatures
* Key factories
* Key generators

---

# 6. How Java Chooses a Provider (Critical Rule)

1. Providers are checked **top-down**
2. First provider that supports the transformation is used
3. Others are ignored

```java
Cipher.getInstance("AES/GCM/NoPadding");
```

➡ Uses **SunJCE** unless overridden.

---

# 7. How to Force a Specific Provider

```java
Cipher.getInstance("AES/XTS/NoPadding", "BC");
```

or

```java
Cipher.getInstance("AES/XTS/NoPadding", new BouncyCastleProvider());
```

---

# 8. Provider Configuration Files

Location:

```text
$JAVA_HOME/conf/security/java.security
```

Contains:

* Provider order
* Disabled algorithms
* Policy restrictions

---

# 9. Provider & FIPS Mode Interaction

| Scenario             | Result     |
| -------------------- | ---------- |
| DES in normal JVM    | ✔ Works    |
| DES in FIPS provider | ❌ Rejected |
| AES/ECB in FIPS      | ❌ Rejected |
| AES/GCM in FIPS      | ✔ Allowed  |

---

# 10. Interview-Ready One-Liners

* **Provider** = Crypto implementation plugin
* **Transformation** = Algorithm + Mode + Padding
* **SunJCE** = Default symmetric crypto
* **Bouncy Castle** = Advanced crypto provider
* **Provider order matters**
* **FIPS providers restrict algorithms**

---

# 11. Recommended Best Practices

✅ Rely on default providers when possible
✅ Explicit provider for non-standard crypto
✅ Log provider name in production
✅ Write provider-aware unit tests

---

## If you want next:

* Provider comparison matrix (SunJCE vs BC vs FIPS)
* How provider order affects security bugs
* How to write provider-agnostic crypto code
* How Java 21 changed crypto providers

Just say the word 👍
