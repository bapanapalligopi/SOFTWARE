Sure! Here's the full content you provided with the same formatting:

---

## **Cryptography Introduction**

**Last Updated: 11 Jul, 2025**

Cryptography is the study and practice of techniques for secure communication in the presence of third parties called adversaries. It deals with developing and analyzing protocols that prevent malicious third parties from retrieving information being shared between two entities, thereby following the various aspects of information security.

**Secure Communication** refers to the scenario where the message or data shared between two parties can’t be accessed by an adversary. In Cryptography, an **Adversary** is a malicious entity, which aims to retrieve precious information or data, thereby undermining the principles of information security. **Data Confidentiality**, **Data Integrity**, **Authentication**, and **Non-repudiation** are core principles of modern-day cryptography.

* **Confidentiality** refers to certain rules and guidelines usually executed under confidentiality agreements that ensure that the information is restricted to certain people or places.
* **Data Integrity** refers to maintaining and ensuring that the data stays accurate and consistent over its entire life cycle.
* **Authentication** is the process of making sure that the piece of data being claimed by the user belongs to it.
* **Non-repudiation** refers to the ability to make sure that a person or a party associated with a contract or a communication cannot deny the authenticity of their signature over their document or the sending of a message.

Consider two parties: **Alice** and **Bob**. Now, Alice wants to send a message **m** to Bob over a secure channel. Here's the process:

1. The **sender’s message** (or sometimes called the **Plaintext**) is converted into an unreadable form using a **Key k**. The resultant text obtained is called the **Ciphertext**. This process is known as **Encryption**.
2. At the time of receiving, the **Ciphertext** is converted back into the **plaintext** using the same **Key k**, so that it can be read by the receiver. This process is known as **Decryption**.

**Mathematically:**

* **Alice (Sender)** → **C = E(m, k)** → **Bob (Receiver)**
* **m = D(C, k)**

Here, **C** refers to the Ciphertext while **E** and **D** are the **Encryption** and **Decryption** algorithms, respectively.

---

### **Example: Caesar Cipher**

Let's consider the case of **Caesar Cipher** or **Shift Cipher** as an example. As the name suggests, in Caesar's Cipher, each character in a word is replaced by another character under some defined rules. For example, if **A** is replaced by **D**, **B** by **E**, and so on, each character in the word would be shifted by a position of 3.

For example:

* **Plaintext:** `Geeksforgeeks`
* **Ciphertext:** `Jhhnvirujhhnv`

**Note:** Even if the adversary knows that the cipher is based on Caesar's Cipher, it cannot predict the plaintext as it doesn’t have the key, which is to shift the characters back by three places.

---

## **Types of Cryptography**

There are several types of cryptography, each with its own unique features and applications. Some of the most common types of cryptography include:

### 1. **Symmetric-key Cryptography**

This type of cryptography involves the use of a **single key** to encrypt and decrypt data. Both the sender and receiver use the **same key**, which must be kept secret to maintain the security of the communication.

### 2. **Asymmetric-key Cryptography**

Asymmetric-key cryptography, also known as **public-key cryptography**, uses a **pair of keys** - a **public key** and a **private key** - to encrypt and decrypt data. The **public key** is available to anyone, while the **private key** is kept secret by the owner.

### 3. **Hash Functions**

A **hash function** is a mathematical algorithm that converts data of any size into a fixed-size output. Hash functions are often used to verify the **integrity** of data and ensure that it has not been tampered with.

---

## **Applications of Cryptography**

Cryptography has a wide range of applications in modern-day communication, including:

1. **Secure Online Transactions:** Cryptography is used to secure online transactions, such as online banking and e-commerce, by encrypting sensitive data and protecting it from unauthorized access.
2. **Digital Signatures:** Digital signatures are used to verify the authenticity and integrity of digital documents and ensure that they have not been tampered with.
3. **Password Protection:** Passwords are often encrypted using cryptographic algorithms to protect them from being stolen or intercepted.
4. **Military and Intelligence Applications:** Cryptography is widely used in military and intelligence applications to protect classified information and communications.

---

## **Challenges of Cryptography**

While cryptography is a powerful tool for securing information, it also presents several challenges, including:

1. **Key Management:** Cryptography relies on the use of **keys**, which must be managed carefully to maintain the security of the communication.
2. **Quantum Computing:** The development of **quantum computing** poses a potential threat to current cryptographic algorithms, which may become vulnerable to attacks.
3. **Human Error:** Cryptography is only as strong as its weakest link, and **human error** can easily compromise the security of a communication.

---

