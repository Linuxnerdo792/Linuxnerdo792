This is a structured summary of your **CEG 3400 Midterm Exam** results. You can copy and paste the Markdown code below into your notes or a `.md` file.

---

# Midterm Exam Results: CEG 3400

**Student:** Sharma Bhattarai

**Date:** Feb 26, 2026

**Score:** 75 / 86 (87.21%)

---

## 1. CIA Triad & Fundamentals

| Question | Topic | Concept | Result |
| --- | --- | --- | --- |
| **1** | Definitions | Confidentiality (Auth access), Integrity (Correct/Authentic), Availability (Accessible) | ✅ 6/6 |
| **2** | Encryption | Primarily ensures **Confidentiality** | ✅ 2/2 |
| **3** | Integrity | Restricting **Write** permissions ensures integrity | ✅ 2/2 |
| **4** | Discord | Anonymity impacts the guarantee of **Confidentiality** | ✅ 2/2 |
| **5** | Hash Sums | Used to verify **Integrity** | ✅ 2/2 |
| **6** | Permissions | Restricting **Read** ensures confidentiality | ✅ 2/2 |
| **7** | Redundancy | GitHub backups ensure **Availability** | ✅ 2/2 |

## 2. Linux Lab & Hashing

* **Q8:** First line of `question-08/a.out`: **Hello World!** ✅
* **Q9:** Salting protects against rainbow tables: **True** ✅
* **Q10:** Higher value KFC coin: **29098sha256sum** ✅
* **Q11:** Can data be retrieved from a hash? **False** ✅
* **Q12:** Max hashes for 10 salts/100 inputs: **1,000** (10 salts × 100 inputs) ❌ *(You chose 10,000)*
* **Q13:** Valid salted MD5 (5-char salt prepended): All 4 options were correct ✅
* **Q14:** Not true of Hash: **"It must transform data to a smaller value"** (Note: Hashes are fixed length, not necessarily smaller) ✅
* **Q15:** Matching SHA256: **executableD** ✅

## 3. Encryption & GPG

* **Q16:** Definitions:
* Steganography: Hiding data in a cover. ✅
* Encryption: Plaintext to Ciphertext. ✅
* Decryption: Ciphertext to Plaintext. ❌ *(Error in matching)*
* Hashing: Fixed length for integrity. ✅


* **Q17:** GPG: **Gnu Privacy Guard** ✅
* **Q18:** Prompt for password: **`gpg --sign`** (requires private key passphrase) ✅
* **Q19:** Signing with public key: **False** (You sign with a *private* key) ✅
* **Q20:** Caesar Cipher `hello` -> `khoor`: **Key = 3** ✅

## 4. Key Exchanges & Asymmetric Crypto

* **Q21:** Matt's Public Key: **All of the above** (Verify, Encrypt, Trust) ✅
* **Q22:** Sending to Kayleigh: Use **Kayleigh's public key** ✅
* **Q23:** Cracked DH (5 mins): **Rotate shared secret every 4 mins** ✅
* **Q24:** Confidentiality vs Crack: **Asymmetric encryption** ❌ *(You chose rotation again)*
* **Q25:** Bonus (Repo check): **File B** ✅

## 5. Authentication & Attacks

* **Q26:** Online attacks require internet: **False** (Local network/Internal systems count) ❌
* **Q27:** Brute force on hash lists: **Offline password attack** ✅
* **Q28:** Best protection: **Multi-factor authentication (MFA)** ✅
* **Q29:** Ford door code attempt: **Online password attack** ✅
* **Q30:** Reduce key presses: **Shoulder surfing** (Watching the code) ❌
* **Q31:** Dictionary attack count: **50** ✅

## 6. File Permissions & Steganography

* **Q32:** `chmod 654`: **-rw-r-xr--** ✅
* **Q33:** SUID bit (`-rws`): Executes as **Owner (bombadil)** ✅
* **Q34:** Checking ACL for "Rob": **Both cat (/etc/group) and getfacl** ❌
* **Q35:** User/Group list: **/etc/group** ✅
* **Q36:** Add second group (ACL): **setfacl** ✅
* **Q37:** Danger of `chmod -R a+r`: **~/.ssh** (Exposes private keys) ✅

---

### Study Note for Mistakes

> [!IMPORTANT]
> * **Q12:** Remember that for salted hashes, the formula is $(\text{Number of Salts}) \times (\text{Number of Potential Inputs})$.
> * **Q24:** While rotation helps, switching to asymmetric encryption (Public Keys) is a more robust way to maintain confidentiality against specific key exchange cracks.
> * **Q26:** "Online" refers to interacting with a live authentication service (like a login page), which doesn't strictly require the "World Wide Web" if the service is on a local network.
> 
> 

Would you like me to explain the logic behind the questions you missed in more detail?
