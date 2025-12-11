Alright, let’s go **from scratch**, step by step, covering every part of your requested topic: **Network Protocols and Key Management in Networking**. I’ll include conceptual explanations, practical usage, commands, file roles, and sample questions with answers. This will be like a **mini-course in one message**.

---

# **1. Network Protocols**

## **HTTP (HyperText Transfer Protocol)**

* Protocol used for **web communication** between browsers and web servers.
* Works on **TCP port 80**.
* **Not encrypted** → data is sent in plain text (passwords, messages).

**Key Points:**

* Stateless: Each request is independent.
* Uses methods like GET, POST, PUT, DELETE.
* GET → fetch data; POST → send data.

---

## **HTTPS (HyperText Transfer Protocol Secure)**

* Secure version of HTTP.
* Uses **SSL/TLS encryption** to secure communication.
* Works on **TCP port 443**.
* Protects against:

  * Eavesdropping
  * Man-in-the-middle attacks

**Key Points:**

* Certificates verify server identity.
* Uses **public-private key cryptography** to encrypt data.

---

## **Certificates & Certificate Authorities (CA)**

* **Certificate:** Proof that a website/server is legitimate.
* Contains:

  * Domain name
  * Owner info
  * Public key
  * Expiration date
  * CA signature
* **Certificate Authority (CA):**

  * Trusted third party that **signs certificates**.
  * Browsers trust CA-signed certificates automatically.
* Self-signed certificates exist but not trusted by default.

**Example workflow:**

1. Browser connects to HTTPS site.
2. Server sends its certificate.
3. Browser checks:

   * Is certificate valid?
   * Is it signed by trusted CA?
4. If yes → secure connection established.

---

# **2. SSH (Secure Shell)**

* Network protocol for **secure remote login**.
* Encrypts all traffic between client and server.
* Works on **TCP port 22**.
* Can be used for:

  * Remote terminal access
  * Secure file transfer (SFTP, SCP)
  * Tunneling

---

## **SSH Key Concepts**

SSH uses **asymmetric cryptography**:

* **Private key:** Keep secret on client machine.
* **Public key:** Share with server in `authorized_keys`.
* **Config file:** Store SSH settings (host, port, user).
* **Known_hosts:** Stores fingerprints of servers you connected to.
* **Authorized_keys:** On server, list of client public keys allowed to connect.

**SSH Workflow:**

1. Client connects to server.
2. Server checks if client's public key is in `authorized_keys`.
3. If yes → secure encrypted connection established.

---

# **3. SSH Commands**

### **ssh**

Connect to a server:

```bash
ssh user@server_ip
```

### **ssh-keygen**

Generate SSH key pair:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

* `-t rsa` → key type
* `-b 4096` → key size
* `-C` → comment

### **sftp**

Secure File Transfer Protocol (interactive mode):

```bash
sftp user@server_ip
```

### **scp**

Copy files securely:

```bash
scp local_file user@server_ip:/remote/path
scp user@server_ip:/remote/file ./local/path
```

---

# **4. Key & Config Files**

| File                        | Purpose                                                    |
| --------------------------- | ---------------------------------------------------------- |
| `private key` (`id_rsa`)    | Keep secret, never share                                   |
| `public key` (`id_rsa.pub`) | Share with server in `authorized_keys`                     |
| `authorized_keys`           | Server file storing public keys allowed to connect         |
| `known_hosts`               | Client file storing fingerprints of servers connected to   |
| `config`                    | Optional client SSH settings (aliases, default user, keys) |

**Example `~/.ssh/config` entry:**

```
Host myserver
    HostName 192.168.1.100
    User research
    IdentityFile ~/.ssh/id_rsa
```

Now you can connect with:

```bash
ssh myserver
```

---

# **5. Using an IP / Network Calculator**

**Purpose:** Calculate subnet ranges, broadcast, network address, etc.

### Example: `ipcalc`

```bash
ipcalc 192.168.1.24/24
```

Outputs:

* Network → `192.168.1.0`
* Netmask → `255.255.255.0`
* Broadcast → `192.168.1.255`
* Host range → `192.168.1.1 – 192.168.1.254`

**Useful for:**

* Assigning IPs in LAN
* Planning subnets
* Checking if host is in subnet

---

# **6. Sample Questions and Answers**

### **HTTP / HTTPS**

1. **Q:** What port does HTTPS use?
   **A:** TCP 443

2. **Q:** Difference between HTTP and HTTPS?
   **A:** HTTPS encrypts traffic using SSL/TLS; HTTP is plain text.

3. **Q:** What is a certificate?
   **A:** A digital document proving server identity.

4. **Q:** What is a CA?
   **A:** Trusted authority that signs certificates.

5. **Q:** Can HTTPS prevent all attacks?
   **A:** No, it only encrypts traffic; server-side vulnerabilities still exist.

---

### **SSH**

1. **Q:** What port does SSH use?
   **A:** TCP 22

2. **Q:** Command to connect via SSH?
   **A:** `ssh user@host`

3. **Q:** Purpose of `authorized_keys`?
   **A:** Stores public keys allowed to access server.

4. **Q:** Difference between public and private key?
   **A:** Private key stays secret; public key is shared with server.

5. **Q:** Command to generate key pair?
   **A:** `ssh-keygen -t rsa -b 4096`

---

### **SFTP / SCP**

1. **Q:** How to upload a file using SCP?
   **A:** `scp file.txt user@host:/path`

2. **Q:** How to download a file using SCP?
   **A:** `scp user@host:/path/file.txt ./`

3. **Q:** Command to enter SFTP interactive mode?
   **A:** `sftp user@host`

4. **Q:** Difference between SCP and SFTP?
   **A:** SCP → simple copy; SFTP → interactive, supports multiple operations.

5. **Q:** How to copy directories with SCP?
   **A:** `scp -r local_dir user@host:/remote/dir`

---

### **SSH Files**

1. **Q:** Where is `known_hosts` located?
   **A:** `~/.ssh/known_hosts`

2. **Q:** Purpose of `config` file?
   **A:** Simplify SSH commands with aliases and default settings.

3. **Q:** How to allow passwordless SSH login?
   **A:** Add client public key to server’s `authorized_keys`.

4. **Q:** Should private keys be shared?
   **A:** No, never share.

5. **Q:** How to specify a custom private key in SSH?
   **A:** `ssh -i /path/to/private_key user@host`

---

### **Network Calculator / IP Subnets**

1. **Q:** What’s the network address of `192.168.1.24/24`?
   **A:** `192.168.1.0`

2. **Q:** Broadcast address?
   **A:** `192.168.1.255`

3. **Q:** How many hosts in `/24`?
   **A:** 254 usable hosts

4. **Q:** Netmask of `/16`?
   **A:** `255.255.0.0`

5. **Q:** How to check if IP belongs to subnet?
   **A:** Use IP calculator or `ipcalc 192.168.1.50/24` → see if network matches.

---

This gives you:

* **Concepts** of HTTP/HTTPS, SSH, Certificates, Keys
* **Commands** & file roles
* **Network calculation basics**
* **Practice questions and answers**

---

If you want, I can **draw a full diagram showing SSH key flow, HTTPS handshake, and network calculation steps**, which makes it super easy to memorize for exams.

Do you want me to make that diagram?
