### Complete Java Cryptography Guide

This document summarizes all the key concepts, classes, algorithms, modes, padding schemes, providers, best practices, and test strategies for cryptography in Java (JCA/JCE). It is structured to serve as a reference for development, interviews, and secure implementation.

---

## 1. Mental Model

**Java Cryptography = Algorithm + Mode + Padding + Provider**

* Algorithms: AES, DES, 3DES, ChaCha20-Poly1305, etc.
* Modes: ECB, CBC, CFB, OFB, CTR, GCM, XTS
* Padding: PKCS5Padding, NoPadding, ISO7816Padding
* Providers: SunJCE, Bouncy Castle, SunPKCS11, SunEC, SUN

Java resolves transformations at runtime via **providers**.

---

## 2. Core APIs

| Class                  | Purpose                      |
| ---------------------- | ---------------------------- |
| Cipher                 | Encryption/Decryption        |
| MessageDigest          | Hashing                      |
| Mac                    | HMAC                         |
| Signature              | Sign/Verify                  |
| KeyGenerator           | Symmetric Key Generation     |
| KeyPairGenerator       | Asymmetric Key Generation    |
| SecretKey              | Symmetric key representation |
| SecureRandom           | Cryptographically secure RNG |
| KeyStore               | Key storage                  |
| AlgorithmParameterSpec | IV/Nonce/Tag parameters      |

---

## 3. Transformation String

Format: `Algorithm / Mode / Padding`

Examples:

* AES/GCM/NoPadding
* AES/CBC/PKCS5Padding
* DESede/CBC/PKCS5Padding
* ChaCha20-Poly1305

---

## 4. Block Cipher Modes

| Mode | IV | Padding | Secure              |
| ---- | -- | ------- | ------------------- |
| ECB  | ❌  | ✔       | ❌                   |
| CBC  | ✔  | ✔       | ⚠️                  |
| CTR  | ✔  | ❌       | ⚠️                  |
| GCM  | ✔  | ❌       | ✔                   |
| XTS  | ✔  | ❌       | ✔ (disk encryption) |

---

## 5. Padding Types

| Padding        | Used With          |
| -------------- | ------------------ |
| PKCS5Padding   | CBC/ECB            |
| NoPadding      | CTR/GCM/XTS        |
| ISO7816Padding | Bouncy Castle only |

---

## 6. IV / Nonce Rules

| Mode     | Size                      |
| -------- | ------------------------- |
| CBC      | Block size (AES=16 bytes) |
| GCM      | 12 bytes recommended      |
| CTR      | Block size                |
| ChaCha20 | 12 bytes                  |

**Never reuse IV/nonce.**

---

## 7. Key Sizes

| Algorithm | Key Sizes           |
| --------- | ------------------- |
| AES       | 128, 192, 256       |
| 3DES      | 168 (112 effective) |
| ChaCha20  | 256                 |
| DES       | ❌ (broken)          |

---

## 8. Providers

| Provider      | Role                                       |
| ------------- | ------------------------------------------ |
| SUN           | Hashing, SecureRandom                      |
| SunJCE        | AES, DES, GCM, CBC                         |
| SunEC         | Elliptic Curve algorithms                  |
| SunJSSE       | TLS                                        |
| SunPKCS11     | HSM integration                            |
| Bouncy Castle | Extended algorithms, AES-XTS, ISO paddings |

Check providers with:

```java
Security.getProviders();
```

---

## 9. Recommended Algorithms (2025)

* ✅ AES/GCM/NoPadding
* ✅ ChaCha20-Poly1305
* ❌ DES
* ❌ 3DES
* ❌ AES/ECB

---

## 10. Secure Coding Template

```java
Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding");
byte[] iv = new byte[12];
SecureRandom.getInstanceStrong().nextBytes(iv);
GCMParameterSpec spec = new GCMParameterSpec(128, iv);
cipher.init(Cipher.ENCRYPT_MODE, key, spec);
byte[] cipherText = cipher.doFinal(plainText);
```

---

## 11. Common Exceptions

| Exception                          | Meaning                 |
| ---------------------------------- | ----------------------- |
| NoSuchAlgorithmException           | Algorithm not supported |
| NoSuchPaddingException             | Invalid padding         |
| InvalidKeyException                | Wrong key               |
| InvalidAlgorithmParameterException | Wrong IV                |
| AEADBadTagException                | Tampering detected      |

---

## 12. Best Practices

**Do:**

* Use AEAD modes (GCM/ChaCha20)
* Use `SecureRandom` for keys/IVs
* Validate provider support
* Write negative tests
* Handle exceptions explicitly

**Don’t:**

* Use ECB mode
* Reuse IV/nonce
* Roll your own crypto
* Hardcode keys
* Ignore provider behavior

---

## 13. Negative Test Scenarios

* AES/CBC with missing or wrong IV
* AES/GCM tampering or wrong key
* ChaCha20 wrong nonce or reused nonce
* Unsupported modes (AES/XTS without BC)
* Invalid padding or tag lengths

---

## 14. Diagram

> Application Code → JCA/JCE → Providers → Provider Implementation → Crypto Operation → Application Code

* Handles keys, IVs, exceptions, transformations
* Provider selection order matters

---

## 15. Interview/Production Summary

> Java cryptography uses a **provider-based architecture**. Algorithms are selected via **transformation strings** and resolved at runtime. Secure usage requires understanding **algorithms, modes, padding, IVs, keys, and providers**. Use AEAD modes, never reuse IV/nonce, and follow provider limitations.

---

This document can serve as a **complete reference** for Java cryptography, combining **best practices, code, tables, negative test scenarios, and architecture overview**.
