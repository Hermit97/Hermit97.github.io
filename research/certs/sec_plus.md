# CompTIA Security+ SY0-701
# The Complete Study Guide
### Built directly from the official CompTIA exam objectives

---

## EXAM AT A GLANCE — KNOW THIS FIRST

| Detail | Value |
|---|---|
| Exam Code | SY0-701 |
| Questions | Maximum 90 (mix of multiple choice + performance-based) |
| Time | 90 minutes |
| Passing Score | 750 out of 900 (~83%) |
| Launched | November 7, 2023 |
| Estimated Retirement | 2026–2027 |

### Domain Weights — Study Accordingly

| Domain | Weight |
|---|---|
| 1.0 General Security Concepts | 12% |
| 2.0 Threats, Vulnerabilities & Mitigations | 22% |
| 3.0 Security Architecture | 18% |
| 4.0 Security Operations | **28%** ← heaviest |
| 5.0 Security Program Management & Oversight | 20% |

### Performance-Based Questions (PBQs)
These are drag-and-drop, fill-in, matching, or scenario simulations. They appear at the START of the exam. Tip: if a PBQ is eating your time, flag it and move on — come back at the end. You have 90 minutes for up to 90 questions, which is 1 minute per question. PBQs often take 3–5 minutes each.

### How CompTIA Words Questions
Watch for keywords:
- **"BEST"** — eliminate wrong answers first, then choose the most complete correct answer
- **"FIRST"** — what do you do BEFORE anything else? (usually: identify/contain)
- **"MOST LIKELY"** — based on the scenario, what fits best?
- **"PREVENT"** — proactive control, not reactive
- **"DETECT"** — detective control, not preventive

---

---

# DOMAIN 1: GENERAL SECURITY CONCEPTS
## Weight: 12% (~10–11 questions)

---

## 1.1 Security Controls

Security controls are the safeguards used to manage risk. The exam tests you on TWO classification systems that work together.

### Control Categories (the "what type of thing is it?")

**Technical Controls** — Technology-based. Things software and hardware do automatically.
- Examples: firewalls, antivirus, encryption, IDS/IPS, access control lists, MFA

**Managerial Controls** — Administrative policies and procedures. Things people decide and write.
- Examples: risk assessments, security policies, background checks, hiring procedures

**Operational Controls** — Day-to-day processes carried out by people.
- Examples: security awareness training, change management procedures, guard patrols, incident response procedures

**Physical Controls** — Tangible things that protect physical access.
- Examples: locks, fences, cameras, badge readers, guards, bollards

### Control Types (the "what does it do?")

**Preventive** — Stops an attack from happening in the first place.
- Examples: firewall rules, encryption, locks, MFA, disabling USB ports

**Deterrent** — Discourages attackers but doesn't physically stop them.
- Examples: warning signs ("Unauthorized access prosecuted"), security cameras visible to would-be attackers, guard presence, login banners

**Detective** — Identifies that an attack has occurred or is occurring.
- Examples: IDS (Intrusion Detection System), log monitoring, SIEM, security cameras (recorded), motion sensors, audit trails

**Corrective** — Minimizes damage and restores systems after an incident.
- Examples: patching a vulnerability after exploitation, restoring from backup, rebooting a crashed system, incident response

**Compensating** — An alternative control used when the ideal control isn't feasible.
- Examples: increased monitoring on an unpatched legacy system (can't patch = compensate with monitoring), manual approval process when automated system is down

**Directive** — Tells people what to do. Policies and procedures.
- Examples: acceptable use policy, security policy, required training, "clean desk" policy

> **Exam Tip:** The exam loves to mix categories and types. A firewall is **Technical + Preventive**. A security camera is **Physical + Detective** (or Deterrent if it's visible). An AUP is **Managerial + Directive**. Know both dimensions simultaneously.

---

## 1.2 Fundamental Security Concepts

### The CIA Triad

The foundation of all information security. Every security control exists to protect one or more of these three properties:

**Confidentiality** — Information is accessible only to authorized parties.
- Threats: eavesdropping, data breaches, insider theft, unencrypted storage
- Controls: encryption, access controls, data classification, need-to-know

**Integrity** — Information is accurate and has not been altered without authorization.
- Threats: man-in-the-middle attacks, unauthorized modification, corruption
- Controls: hashing, digital signatures, file integrity monitoring, checksums

**Availability** — Systems and data are accessible to authorized users when needed.
- Threats: DDoS attacks, hardware failure, natural disasters, ransomware
- Controls: redundancy, backups, UPS, load balancing, failover systems

> **Non-repudiation** — The ability to prove that a specific party performed a specific action. You cannot deny having done something. Achieved through digital signatures and audit logs. Example: a digitally signed email proves the sender's identity because only they have the private key.

### AAA Framework — Authentication, Authorization, Accounting

These three concepts govern how identity and access are managed:

**Authentication** — Proving you are who you claim to be.
- Authenticating people: username/password, biometrics, smart cards, MFA
- Authenticating systems: certificates, pre-shared keys, device fingerprinting

**Authorization** — What are you allowed to do after you're authenticated?
- Authorization models: Role-Based Access Control (RBAC), Discretionary (DAC), Mandatory (MAC), Rule-based
- Principle of least privilege: grant only the minimum access needed

**Accounting (Auditing)** — Tracking what authenticated, authorized users actually do.
- Log files, audit trails, SIEM, timestamps
- Used for forensics, compliance, detecting insider threats

### Gap Analysis

A gap analysis compares your current security posture to a desired target state (a framework, standard, or baseline). It identifies what controls are missing or insufficient.
- "We want to meet NIST CSF requirements. Here's where we currently fall short."
- Output: a list of gaps to be remediated, usually prioritized by risk.

### Zero Trust

Zero Trust is an architectural philosophy, not a single product. The core principle: **"Never trust, always verify."** Even users inside the network perimeter are not automatically trusted.

**Control Plane** — Where decisions about access are made:
- **Policy Engine** — Evaluates requests using policy and risk signals to make allow/deny decisions
- **Policy Administrator** — Communicates decisions from the Policy Engine to the enforcement points
- **Adaptive identity** — Continuously evaluates identity signals (user behavior, device health, location) rather than authenticating once and granting persistent trust
- **Threat scope reduction** — Limit the blast radius if something is compromised
- **Policy-driven access control** — Access is determined by policy, not by location on the network

**Data Plane** — Where traffic actually flows, where enforcement happens:
- **Policy Enforcement Point (PEP)** — The gate. Allows or blocks traffic based on Policy Administrator decisions
- **Subject/System** — The user or device requesting access
- **Implicit trust zones** — In Zero Trust, these are minimized or eliminated. Traditional networks had implicit trust inside the firewall.

### Physical Security

The exam tests physical security concepts with surprisingly specific terminology:

- **Bollards** — Sturdy posts embedded in the ground to prevent vehicle ramming
- **Access control vestibule** — A small room with two doors where one must close before the other opens (also called a mantrap). Prevents tailgating.
- **Fencing** — Perimeter control. Chain-link is deterrent; concrete/anti-climb is stronger
- **Video surveillance** — Cameras for detection and deterrence. Placement matters.
- **Security guard** — Operational/physical deterrent and detective control
- **Access badge** — Physical + technical control for building access
- **Lighting** — Deterrent; reduces concealment opportunities
- **Sensors:**
  - **Infrared** — Detects heat signatures (body heat); used in motion detection
  - **Pressure** — Detects weight on a surface (floor mats, pressure plates)
  - **Microwave** — Emits microwave pulses and detects reflections; wide-area motion detection
  - **Ultrasonic** — Emits ultrasonic sound and detects changes; used in motion sensors

### Deception and Disruption Technology

These are tools designed to deceive attackers and alert defenders:

- **Honeypot** — A fake system that looks valuable but is actually monitored. Any access to it is inherently suspicious. Used to detect and study attackers.
- **Honeynet** — A network of honeypots. Simulates an entire fake network environment.
- **Honeyfile** — A fake file (like "Passwords.xlsx") placed in a location where legitimate users would have no reason to open it. If it's opened, you know you have an intruder or insider threat.
- **Honeytoken** — A fake credential, API key, or data record embedded in a system. If it's used, you detect a breach. (A honeyfile is a specific type of honeytoken.)

---

## 1.3 Change Management and Security

Change management controls the process of making modifications to IT systems to prevent unauthorized or poorly tested changes from introducing vulnerabilities.

### Business Processes

- **Approval process** — Changes must be reviewed and approved (often by a Change Advisory Board, CAB) before implementation
- **Ownership** — Every asset and change has an identified owner who is accountable
- **Stakeholders** — People who have interest in the change; must be consulted
- **Impact analysis** — Assess how the change could affect security, availability, and business operations
- **Test results** — Changes should be tested in a non-production environment first
- **Backout plan** — Every change needs a documented procedure to reverse it if something goes wrong
- **Maintenance window** — The approved time period during which changes can be made (usually off-hours)
- **Standard operating procedure (SOP)** — Documented step-by-step instructions for performing the change

### Technical Implications of Changes

- **Allow lists / Deny lists** — Applications that are permitted or blocked from running; changes to software require updating these lists
- **Restricted activities** — Some changes require special authorization (e.g., firewall rule changes)
- **Downtime** — Some changes require taking systems offline; plan and communicate this
- **Service restart / Application restart** — Changes may require restarting services, which temporarily disrupts access
- **Legacy applications** — Older applications may not tolerate changes well; treat them carefully
- **Dependencies** — A change to one system may affect dependent systems; must be mapped

### Documentation

- **Updating diagrams** — Network diagrams, data flow diagrams must be updated to reflect changes
- **Updating policies/procedures** — If the change affects how things are done, the documentation must follow

### Version Control

All configuration files, scripts, and code should be stored in a version control system. This provides: change history, rollback capability, accountability, and auditability.

---

## 1.4 Cryptography

This is a heavily tested section. Know every concept here.

### Public Key Infrastructure (PKI)

PKI is the framework of policies, hardware, software, and procedures for creating, managing, distributing, using, storing, and revoking digital certificates.

**Public Key** — Available to anyone. Used to encrypt data sent to the key owner, or to verify a digital signature made by the key owner.

**Private Key** — Known only to the owner. Used to decrypt data encrypted with the corresponding public key, or to create digital signatures.

> **Memory trick:** If Alice wants to send Bob an encrypted message, Alice encrypts with **Bob's public key**. Only Bob can decrypt it with **Bob's private key**. For signing: Bob signs with his **private key**; anyone with Bob's **public key** can verify the signature.

**Key Escrow** — A copy of a private key is held by a trusted third party. Allows recovery of encrypted data if the key owner loses their key. Required by some organizations/governments for law enforcement access.

### Encryption Levels

Know WHERE encryption is applied:

- **Full-disk encryption (FDE)** — Encrypts the entire hard drive (e.g., BitLocker, FileVault). Protects data if the physical device is stolen.
- **Partition encryption** — Encrypts a specific partition on a drive, not the whole disk
- **File encryption** — Encrypts individual files (e.g., EFS - Encrypting File System on Windows)
- **Volume encryption** — Encrypts a specific volume/container (e.g., VeraCrypt volume)
- **Database encryption** — Encrypts the entire database or specific tables
- **Record encryption** — Encrypts individual records or fields within a database (most granular)
- **Transport/communication encryption** — Encrypts data as it travels over a network (TLS, HTTPS, VPN)

### Symmetric vs. Asymmetric Encryption

**Symmetric encryption:**
- Same key for encryption AND decryption
- Fast — suitable for bulk data encryption
- Problem: key distribution (how do you securely share the key with someone?)
- Examples: AES (Advanced Encryption Standard) — the gold standard today; DES (old, 56-bit, broken); 3DES (deprecated); RC4 (stream cipher, deprecated)

**Asymmetric encryption:**
- Different keys: public key encrypts, private key decrypts (or private signs, public verifies)
- Slow — not used for bulk data; used for key exchange and digital signatures
- Examples: RSA, ECC (Elliptic Curve Cryptography), Diffie-Hellman (key exchange)

**Key Exchange** — In practice, asymmetric encryption is used to securely exchange a symmetric key, then symmetric encryption does the actual data transfer. This is exactly how TLS works.

**Algorithms to Know:**
- **AES** — Symmetric. Block cipher. Key sizes: 128, 192, 256-bit. Current standard.
- **RSA** — Asymmetric. Based on difficulty of factoring large numbers. Key size 2048+ bit recommended.
- **ECC** — Asymmetric. Smaller key sizes for equivalent security. Efficient for mobile.
- **Diffie-Hellman (DH)** — Key exchange protocol. Allows two parties to establish a shared secret over an insecure channel. **DHE** (Ephemeral) generates new keys for each session = Perfect Forward Secrecy.
- **SHA (Secure Hash Algorithm)** — SHA-256, SHA-512 are current standards. Produces fixed-length hashes.
- **MD5** — Older hash algorithm, 128-bit. Considered cryptographically broken (collision attacks). Still used for file integrity checks, not for security.

**Key Length** — Longer keys = more security but slower performance. 
- Symmetric: 128-bit minimum, 256-bit preferred
- Asymmetric RSA: 2048-bit minimum, 4096-bit for high security
- ECC: 256-bit provides similar security to RSA 3072-bit

### Cryptographic Tools and Hardware

**Trusted Platform Module (TPM)** — A chip embedded on the motherboard that provides hardware-based cryptographic functions: key storage, random number generation, and platform attestation (proving the system hasn't been tampered with). BitLocker uses TPM.

**Hardware Security Module (HSM)** — A dedicated hardware device for cryptographic operations and key management. Used in enterprise environments for certificate authorities, payment systems, and high-value key protection. More powerful than TPM.

**Key Management System (KMS)** — Software for managing the lifecycle of cryptographic keys: generation, distribution, rotation, and revocation.

**Secure Enclave** — A protected region of a processor that runs isolated code. On Apple devices, the Secure Enclave stores biometric data and encryption keys. Intel SGX is a similar technology.

### Obfuscation Techniques

These techniques make data harder to understand without actually encrypting it (though they're often combined with encryption):

**Steganography** — Hiding data inside other data. Example: embedding secret text inside a JPEG image. The image looks normal but contains hidden data. Not encryption — the data isn't scrambled, just hidden.

**Tokenization** — Replacing sensitive data with a non-sensitive placeholder (a "token"). The mapping between token and real value is stored in a separate, secure token vault. Example: credit card numbers replaced with tokens in a payment system. The token can be used for transactions but is useless if stolen.

**Data Masking** — Replacing real data with realistic-looking fake data. Used for test environments where you need data that looks real but isn't. Example: showing only the last 4 digits of a credit card number.

### Hashing

A hash function takes input of any size and produces a fixed-length output (the hash/digest). Properties:
- **One-way** — You cannot reverse a hash to get the original data
- **Deterministic** — Same input always produces the same output
- **Collision-resistant** — It should be computationally infeasible to find two different inputs that produce the same hash
- Used for: file integrity verification, password storage, digital signatures

**Salting** — Adding a random value (salt) to a password before hashing it. Prevents pre-computed rainbow table attacks. Two users with the same password will have different hashes because their salts differ. Salts are stored alongside the hash.

**Key Stretching** — Using an algorithm to deliberately make password hashing slow, making brute-force attacks impractical. Examples: bcrypt, PBKDF2, Argon2. Each uses many iterations of a hash function.

### Digital Signatures

A digital signature proves:
1. **Authenticity** — The message came from who it claims it did
2. **Integrity** — The message has not been altered
3. **Non-repudiation** — The sender cannot deny signing it

Process: Sender creates a hash of the message → encrypts the hash with their **private key** (this is the signature) → attaches it to the message. Receiver decrypts the signature with the sender's **public key** to get the hash → independently hashes the received message → if the hashes match, the signature is valid.

### Blockchain

A distributed, immutable ledger. Transactions are grouped into blocks, each containing a hash of the previous block, forming a chain. Altering any block invalidates all subsequent blocks, making tampering evident. Used for: cryptocurrency, supply chain tracking, digital contracts.

**Open public ledger** — A blockchain that is publicly readable and verifiable by anyone (like Bitcoin). Anyone can audit the history of transactions.

### Certificates and PKI Infrastructure

**Certificate Authority (CA)** — A trusted entity that issues digital certificates. Verifies that a public key belongs to the claimed owner and digitally signs the certificate to prove authenticity.
- **Root CA** — The top of the trust hierarchy. Its certificate is self-signed. Often kept offline for security.
- **Intermediate CA** — Sits between the Root CA and end-entity certificates. Root CA signs the Intermediate CA cert, which then signs user/server certificates. This protects the Root CA.

**Certificate Revocation List (CRL)** — A list published by the CA containing serial numbers of revoked certificates. Clients download the CRL to check if a certificate has been revoked. Problem: CRLs can be large and slow to check.

**Online Certificate Status Protocol (OCSP)** — A real-time method for checking certificate revocation status. More efficient than CRLs — the client queries the OCSP responder for a specific certificate.

**Self-Signed Certificate** — A certificate signed by the entity that created it (not by a CA). No third-party trust established. Browsers show "Not Secure" warnings. Used internally or for testing.

**Third-Party Certificate** — Signed by a trusted public CA (like DigiCert, Let's Encrypt). Trusted by browsers and operating systems automatically.

**Root of Trust** — The starting point of a trust chain. If you trust the Root CA, you implicitly trust everything it has signed (within the chain). TPM is hardware root of trust. Root CA is PKI root of trust.

**Certificate Signing Request (CSR)** — A message sent to a CA to request a certificate. Contains the applicant's public key and identifying information (organization, domain name). The CA verifies this information, signs the public key, and returns the certificate.

**Wildcard Certificate** — A single certificate valid for a domain and all its subdomains. Example: `*.example.com` covers `www.example.com`, `mail.example.com`, `shop.example.com`. If the private key is compromised, all subdomains are at risk.

---

## Domain 1 Practice Questions

**1.** An organization cannot patch a critical legacy system due to application compatibility issues. They implement additional logging and monitoring on that system instead. What type of security control is this?

A) Corrective  
B) Preventive  
C) Compensating  
D) Deterrent

**Answer: C — Compensating.** When the ideal control (patching) cannot be implemented, an alternative control (monitoring) is used. This is the definition of a compensating control.

---

**2.** A company places visible security cameras at all building entrances but doesn't actively monitor the footage in real time. What is the PRIMARY security function of these cameras?

A) Detective  
B) Corrective  
C) Deterrent  
D) Preventive

**Answer: C — Deterrent.** Visible cameras that aren't actively monitored primarily discourage bad behavior. If they were actively monitored and generated alerts, they'd also be detective. The PRIMARY function of a visible-but-unmonitored camera is deterrence.

---

**3.** Which component of the Zero Trust architecture is responsible for evaluating access requests and making allow/deny decisions based on policy?

A) Policy Enforcement Point  
B) Policy Administrator  
C) Policy Engine  
D) Adaptive Identity

**Answer: C — Policy Engine.** The Policy Engine evaluates and makes the decision. The Policy Administrator communicates that decision. The Policy Enforcement Point enforces it.

---

**4.** An employee signs an important contract using a digital signature. Later, they claim they never signed it. Which security concept BEST addresses this situation?

A) Confidentiality  
B) Non-repudiation  
C) Integrity  
D) Authentication

**Answer: B — Non-repudiation.** Digital signatures provide non-repudiation — the signer cannot credibly deny signing the document because only they have the private key.

---

**5.** A security team places a file named "ExecutiveCompensation2024.xlsx" in a network share. The file contains no real data, but any access to it triggers an alert. This is an example of:

A) Honeypot  
B) Honeyfile  
C) Honeynet  
D) Steganography

**Answer: B — Honeyfile.** A honeyfile is a fake file designed to attract unauthorized access and trigger an alert when opened.

---

**6.** Which encryption method uses the same key for both encryption and decryption and is best suited for encrypting large amounts of data?

A) Asymmetric encryption  
B) Public key encryption  
C) Symmetric encryption  
D) Hashing

**Answer: C — Symmetric encryption.** Symmetric uses the same key for both operations and is faster, making it suitable for bulk data. Asymmetric is slower and used for key exchange and signatures.

---

**7.** Which of the following BEST prevents rainbow table attacks against stored passwords?

A) Key stretching  
B) Salting  
C) Tokenization  
D) Hashing

**Answer: B — Salting.** Rainbow tables are pre-computed hash tables for common passwords. Salting adds a unique random value to each password before hashing, making pre-computed tables useless because each user's hash is unique even for the same password. (Note: key stretching helps against brute force; salting specifically defeats rainbow tables.)

---

**8.** A CSR has been submitted to a CA. What does the CA return after verifying and approving the request?

A) A public key  
B) A private key  
C) A digital certificate  
D) A CRL entry

**Answer: C — A digital certificate.** The CA signs the public key included in the CSR and returns a digital certificate binding the public key to the verified identity.

---

---

# DOMAIN 2: THREATS, VULNERABILITIES & MITIGATIONS
## Weight: 22% (~19–20 questions)

---

## 2.1 Threat Actors and Motivations

### Threat Actors

**Nation-State** — Governments sponsoring cyber operations. Characteristics: highly sophisticated, nearly unlimited resources, long-term persistent campaigns, geopolitical objectives. Also called Advanced Persistent Threats (APTs). Examples: Russia's Fancy Bear, China's APT41.

**Unskilled Attacker (Script Kiddie)** — Uses existing tools and exploits written by others without deep understanding. Low sophistication, low funding, often motivated by curiosity or bragging rights.

**Hacktivist** — Motivated by ideological, political, or social causes. Techniques include DDoS and website defacement. Examples: Anonymous.

**Insider Threat** — Someone with legitimate access who misuses it. Can be malicious (intentional harm) or negligent (accidental). Hardest to detect because they already have authorized access. Includes: employees, contractors, former employees with revoked credentials.

**Organized Crime** — Criminal groups primarily motivated by financial gain. Capabilities approaching nation-state level in some cases. Operate ransomware-as-a-service, banking fraud, data theft for sale on dark web.

**Shadow IT** — Not a traditional "attacker" but a threat actor category. Refers to IT systems, software, or services used within an organization without explicit IT department approval. Introduces vulnerabilities because they're outside the security team's visibility.

### Attributes of Threat Actors

- **Internal vs. External** — Insiders have network access; external actors must penetrate the perimeter first
- **Resources/Funding** — Nation-states have nearly unlimited resources; script kiddies have minimal
- **Level of sophistication/capability** — Script kiddies use existing tools; nation-states develop zero-days

### Motivations

Know the reason behind attacks:
- **Data exfiltration** — Stealing data (trade secrets, PII, credentials)
- **Espionage** — Intelligence gathering (often nation-state)
- **Service disruption** — Denial of service, business disruption (hacktivists, competitors, ransomware)
- **Blackmail** — Extortion (ransomware, threatening to release embarrassing data)
- **Financial gain** — The dominant motivation for organized crime
- **Philosophical/political beliefs** — Hacktivists
- **Ethical** — "Ethical" hackers who believe they're doing good by exposing vulnerabilities (but without authorization, they're still criminals)
- **Revenge** — Disgruntled former employees
- **Disruption/chaos** — Creating disorder without clear strategic goal
- **War** — Cyber warfare as part of nation-state armed conflict

---

## 2.2 Threat Vectors and Attack Surfaces

### Message-Based Vectors

**Email** — The dominant delivery mechanism for malware and phishing. Can carry: malicious attachments, malicious links, business email compromise.

**SMS (Short Message Service)** — Text message-based attacks. Often used in smishing.

**Instant Messaging (IM)** — Slack, Teams, Discord used to send malicious links and files.

### Other Attack Vectors

**Image-based** — Malicious code hidden in image files. Steganography or exploiting image processing vulnerabilities.

**File-based** — Malicious documents (Word, Excel with macros), PDFs, scripts.

**Voice call** — Vishing (voice phishing). Attacker calls posing as IT support, bank, IRS.

**Removable device** — USB drives left in parking lots (baiting). Can carry malware that auto-executes.

**Vulnerable software:**
- **Client-based** — Software installed on the client (browser, Office) with a vulnerability
- **Agentless** — Vulnerabilities in systems accessed without an installed agent

**Unsupported systems** — Software/OS past end-of-life (EOL). No more patches. Every newly discovered vulnerability is a permanent vulnerability.

**Unsecure networks:**
- **Wireless** — Open Wi-Fi, weak encryption (WEP, old WPA), rogue access points
- **Wired** — Physical access to unprotected Ethernet ports
- **Bluetooth** — BlueJacking (sending unsolicited messages), BlueSnarfing (unauthorized data access)

**Open service ports** — Unnecessary services listening on open ports expand the attack surface.

**Default credentials** — Factory-set usernames/passwords (admin/admin) never changed. Automated scanners specifically target these.

**Supply chain** — Attacking through trusted vendors, managed service providers (MSPs), or hardware/software suppliers. If an attacker compromises a software vendor's update server, they can deliver malware to all customers.

### Social Engineering and Human Vectors

Social engineering exploits human psychology rather than technical vulnerabilities.

**Phishing** — Fraudulent email appearing to come from a trusted source. Tricks recipients into clicking links, opening attachments, or providing credentials.

**Vishing** — Voice phishing. Phone calls from fake IT support, banks, or government agencies.

**Smishing** — SMS phishing. Text messages with malicious links.

**Spear phishing** — Targeted phishing aimed at a specific individual or organization. Highly personalized = more convincing.

**Whaling** — Spear phishing targeting high-value executives (CEO, CFO).

**Misinformation/Disinformation** — Spreading false information to influence decisions or create confusion. Misinformation: false info spread unknowingly. Disinformation: false info spread deliberately.

**Impersonation** — Pretending to be someone else (IT support, vendor, executive).

**Business Email Compromise (BEC)** — Attacker compromises or spoofs a business email account (often the CEO or CFO) to authorize fraudulent wire transfers or data requests.

**Pretexting** — Creating a fabricated scenario (pretext) to extract information. "I'm calling from IT and need your password to reset your account."

**Watering hole** — Attacker compromises a website frequently visited by the target (the "watering hole"). When targets visit, they get infected. Used against organizations with good email defenses.

**Brand impersonation** — Fake websites, emails, or social media pages using legitimate brand logos and style.

**Typosquatting** — Registering misspelled versions of popular domain names (gooogle.com, paypa1.com) to catch users who mistype. Also called URL hijacking.

---

## 2.3 Types of Vulnerabilities

### Application Vulnerabilities

**Memory Injection** — Injecting malicious code into a running process's memory. Allows attackers to execute arbitrary code in the context of a trusted process. Used by many malware families to evade detection.

**Buffer Overflow** — Writing more data to a memory buffer than it can hold, overwriting adjacent memory. Can overwrite the return address of a function to redirect execution to attacker-controlled code. Classic vulnerability class; prevented by input validation and modern protections like ASLR (Address Space Layout Randomization) and DEP (Data Execution Prevention).

**Race Conditions** — Two or more processes access shared data concurrently, and the outcome depends on timing. Security relevant:
- **Time-of-check (TOC)** — When the state is checked
- **Time-of-use (TOU)** — When the state is actually used
- **TOCTOU attack** — Attacker modifies data between the check and the use. Example: checking file permissions before reading but attacker swaps the file between check and read.

**Malicious Update** — Software update mechanisms that aren't properly verified can be hijacked to deliver malware instead of legitimate updates. SolarWinds was a supply-chain/malicious-update attack.

### OS-Based Vulnerabilities

Vulnerabilities in the operating system kernel or core components. Privilege escalation exploits are common — gaining administrative access from a limited user account.

### Web-Based Vulnerabilities

**SQL Injection (SQLi)** — Inserting malicious SQL code into input fields that are passed to a database. Can allow reading, modifying, or deleting database contents, bypassing authentication.

Example: Login form that builds the query: `SELECT * FROM users WHERE username='$input'`
Attacker enters: `' OR '1'='1` → query becomes always-true, bypassing authentication.

**Cross-Site Scripting (XSS)** — Injecting malicious client-side scripts (usually JavaScript) into web pages viewed by other users. Two types:
- **Stored/Persistent XSS** — Malicious script is stored on the server (in a comment, post, etc.) and executes whenever any user views that content
- **Reflected XSS** — Malicious script is in the URL, reflected back in the server's response; requires tricking the victim into clicking a crafted link

### Hardware Vulnerabilities

**Firmware** — The low-level software embedded in hardware devices. Firmware vulnerabilities are difficult to patch and can persist even after OS reinstall.

**End-of-Life (EOL)** — Hardware no longer supported by the manufacturer. No security patches. Must be replaced or isolated.

**Legacy hardware** — Older hardware that may have known vulnerabilities or lack modern security features.

### Virtualization Vulnerabilities

**VM Escape** — A critical vulnerability where code running inside a virtual machine breaks out to execute on the hypervisor or host operating system. If successful, the attacker can compromise all VMs on the same physical host.

**Resource Reuse** — When a VM is deleted, its previously used memory, storage, or CPU resources may be allocated to a new VM without being properly wiped. The new VM might read residual data from the previous tenant.

### Cloud-Specific Vulnerabilities

- Misconfigured cloud storage (S3 buckets set to public)
- Insufficient identity controls
- Insecure APIs
- Shared responsibility model misunderstandings (customers assume the cloud provider protects more than they actually do)

### Supply Chain Vulnerabilities

**Service provider** — If your managed service provider is compromised, they can be a vector into your network (Kaseya VSA attack).
**Hardware provider** — Counterfeit or tampered hardware. Malicious chips installed during manufacturing.
**Software provider** — Malicious code inserted into legitimate software before distribution (SolarWinds SUNBURST).

### Cryptographic Vulnerabilities

- Using weak/deprecated algorithms (MD5, DES, RC4)
- Poor random number generation
- Using small key sizes
- Improper key storage

### Misconfiguration

The most common vulnerability class. Default credentials, unnecessary services enabled, overly permissive firewall rules, unnecessary open ports, permissions set too broadly.

### Mobile Device Vulnerabilities

**Side loading** — Installing apps from sources other than the official app store. These apps haven't undergone the app store's security review.

**Jailbreaking (iOS) / Rooting (Android)** — Removing manufacturer restrictions to gain elevated privileges. Bypasses many security controls. Makes the device more vulnerable.

### Zero-Day

A vulnerability that is unknown to the software vendor and therefore has no patch available. "Zero days" because the vendor has had zero days to fix it. Highly valuable to attackers. Nation-states stockpile zero-days. Once a vendor is notified and releases a patch, it's no longer a zero-day (it becomes a known vulnerability).

---

## 2.4 Indicators of Malicious Activity

### Malware Types

**Ransomware** — Encrypts victim's files and demands payment for the decryption key. Modern variants also exfiltrate data before encrypting (double extortion). Spread via phishing, RDP compromise, software vulnerabilities.

**Trojan** — Malware disguised as legitimate software. Unlike a virus, it doesn't self-replicate. The user installs it thinking it's something useful.

**Worm** — Self-replicating malware that spreads without user interaction by exploiting network vulnerabilities. WannaCry was a worm (exploited EternalBlue/MS17-010). Worms can spread at machine speed, infecting entire networks rapidly.

**Spyware** — Covertly monitors user activity (browsing, keystrokes, screenshots) and reports it to the attacker. May be used by advertisers or stalkerware operators.

**Bloatware** — Unwanted software pre-installed on devices. Not always malicious but wastes resources and can be a security risk.

**Virus** — Malicious code that attaches to or inserts itself into legitimate programs or files. Requires user action to spread (opening an infected file). Infects other files on the same system.

**Keylogger** — Records keystrokes. Captures passwords, credit card numbers, and other sensitive information typed by the user. Can be hardware (physical device) or software.

**Logic Bomb** — Code that executes when a specific condition is met (a date, a user account being deleted, a specific string typed). Designed to be dormant and difficult to detect.

**Rootkit** — Malware designed to hide itself and other malware from the operating system and security tools. Often operates at a deep level (kernel, bootloader). Very difficult to detect and remove. Requires bootable antivirus or reimaging.

### Physical Attacks

**Brute force (physical)** — Physically forcing entry: kicking down doors, breaking locks. Also used to refer to jamming badge readers.

**RFID Cloning** — Reading and duplicating an RFID chip (access badge, contactless payment card) using a handheld scanner, then creating a clone to gain unauthorized access.

**Environmental** — Attacks on physical infrastructure: cutting power, HVAC manipulation (causing overheating), water damage.

### Network Attacks

**Distributed Denial-of-Service (DDoS)** — Overwhelming a target with traffic from many sources (a botnet) to deny service to legitimate users.
- **Amplified DDoS** — Attacker sends small requests to servers with the victim's spoofed IP. Servers send large responses to the victim. DNS, NTP, memcached are common amplifiers. Small attacker bandwidth creates massive flood.
- **Reflected DDoS** — Using third-party servers as "reflectors" to bounce attack traffic toward the victim, hiding the attacker's origin.

**DNS Attacks:**
- **DNS Spoofing/Cache Poisoning** — Inserting false DNS records into a resolver's cache, redirecting users to malicious sites
- **DNS Hijacking** — Compromising DNS settings on a router or computer to redirect all DNS queries
- **DNS Tunneling** — Using DNS queries to exfiltrate data or create a covert command-and-control channel

**Wireless Attacks:**
- **Evil Twin** — A rogue Wi-Fi access point with the same SSID as a legitimate network. Victims connect and their traffic is intercepted.
- **Deauthentication (Deauth) attack** — Sending forged deauthentication frames to disconnect clients from a legitimate AP, forcing them to reconnect (possibly to an evil twin) or to capture the WPA handshake.
- **WPS Attack** — WPS (Wi-Fi Protected Setup) has a design flaw allowing the PIN to be brute-forced relatively quickly.

**On-path attack (formerly MitM - Man-in-the-Middle)** — Attacker secretly intercepts and potentially alters communication between two parties who believe they are communicating directly with each other. ARP poisoning, DNS spoofing, and rogue APs enable on-path attacks.

**Credential Replay** — Capturing valid authentication credentials and reusing them to gain unauthorized access without cracking them. Pass-the-Hash (PtH) is a replay attack using captured Windows NTLM hash values.

**Malicious Code** — Broad category: any code that performs unauthorized actions.

### Application Attacks

**Injection** — Inserting malicious code/commands into input that is executed by the application. SQLi is the most common. Also: command injection (OS commands), LDAP injection, XML injection.

**Buffer Overflow** — (see vulnerabilities section above)

**Replay attack** — Capturing valid data transmission and reusing it later. Countermeasure: timestamps, sequence numbers, nonces.

**Privilege Escalation** — Gaining higher privileges than authorized.
- Vertical privilege escalation: regular user → admin
- Horizontal privilege escalation: user A accessing user B's data

**Forgery — Cross-Site Request Forgery (CSRF/XSRF)** — A malicious website tricks a user's browser into making unauthorized requests to another website where the user is authenticated. Example: visiting attacker.com triggers a bank transfer on yourbank.com. Countermeasure: CSRF tokens.

**Directory Traversal** — Using "../" sequences in input to navigate outside the intended directory and access files elsewhere on the server. Example: `https://example.com/files?name=../../../../etc/passwd`

### Cryptographic Attacks

**Downgrade attack** — Forcing a connection to use a weaker, older version of a protocol or cipher that is easier to crack. Example: POODLE attack forced TLS connections to fall back to SSL 3.0.

**Collision attack** — Finding two different inputs that produce the same hash output. If successful against a hash used for digital signatures, an attacker could create a malicious document with the same hash as a legitimate one.

**Birthday attack** — A collision attack based on the birthday paradox (in a group of 23 people, there's a 50% chance two share a birthday). For hash functions: finding any two inputs with the same hash is much faster than finding an input that matches a specific hash.

### Password Attacks

**Password spraying** — Trying a small number of common passwords (like "Password1!") against a large number of accounts. Evades account lockout policies because few attempts per account. More effective than brute force against real environments.

**Brute force** — Systematically trying every possible combination. Very slow for complex passwords. Works offline against captured password hashes.

### Indicators

These are signs that something bad may be happening:

- **Account lockout** — Multiple failed authentication attempts, possibly brute force or password spray
- **Concurrent session usage** — Same user account logged in from multiple locations simultaneously (stolen credentials)
- **Blocked content** — DLP or web filter triggering on unusual data patterns
- **Impossible travel** — User authenticated from New York at 9 AM and London at 9:30 AM (impossible to travel that fast)
- **Resource consumption** — Unusual spikes in CPU, memory, network, disk (cryptomining, DDoS participation, data exfiltration)
- **Resource inaccessibility** — Systems suddenly unavailable (ransomware encryption, DDoS)
- **Out-of-cycle logging** — Log entries at unusual times (3 AM activity on a normally quiet system)
- **Published/documented** — Known indicators appearing in threat intel feeds
- **Missing logs** — Logs that should exist don't (attacker may have deleted evidence, or logging was disabled)

---

## 2.5 Mitigation Techniques

**Segmentation** — Dividing a network into smaller zones. Limits lateral movement — a compromised system in one segment can't easily reach systems in others. VLANs, subnets, firewalls between segments.

**Access Control:**
- **ACL (Access Control List)** — Rules defining who/what can access a resource. Firewalls use ACLs.
- **Permissions** — File and folder access rights (read, write, execute)

**Application Allow List** — Only approved applications are permitted to run. Everything else is blocked by default. Very effective but operationally challenging. Contrast with deny list (blacklist), which blocks known bad things but allows everything else.

**Isolation** — Separating a system completely from others. Air-gapping critical systems (no network connectivity at all).

**Patching** — Applying software updates to fix known vulnerabilities. The single most impactful mitigation. Must be done systematically and quickly, especially for critical vulnerabilities.

**Encryption** — Encrypting data at rest and in transit so it's useless if intercepted or stolen.

**Monitoring** — Continuous visibility into what's happening on systems and networks. SIEM, log aggregation, UEBA.

**Least Privilege** — Grant users and systems only the minimum access required to perform their function. Limits damage if credentials are compromised.

**Configuration Enforcement** — Ensuring systems remain in their desired secure configuration. Drift (unauthorized changes) is monitored and corrected. Tools: MDM, configuration management, CIS Benchmarks.

**Decommissioning** — Properly retiring systems at end-of-life. Includes data sanitization, license release, and removal from inventory.

**Hardening Techniques:**
- **Encryption** — Enable disk encryption, transit encryption
- **Install endpoint protection** — Antivirus, EDR
- **Host-based firewall** — Enable and configure the OS firewall
- **HIPS (Host-based Intrusion Prevention System)** — Monitors and blocks malicious activity at the host level
- **Disable unnecessary ports/protocols** — Reduce attack surface
- **Change default passwords** — First thing to do on any new device
- **Remove unnecessary software** — Eliminate unused software that could be exploited

---

## Domain 2 Practice Questions

**1.** An attacker sends a flood of DNS queries to open resolvers with the victim's IP address forged as the source. The resolvers send large DNS responses to the victim. What type of attack is this?

A) DNS Hijacking  
B) DNS Tunneling  
C) Amplified DDoS  
D) Reflected DDoS

**Answer: C — Amplified DDoS.** Small queries generate large responses, amplifying the attack traffic. The DNS servers act as unwitting amplifiers.

---

**2.** A user receives an email appearing to come from their bank, directing them to click a link and enter their credentials. The website looks identical to their real bank. What attack is this?

A) Vishing  
B) Smishing  
C) Whaling  
D) Phishing

**Answer: D — Phishing.** This is a classic email-based phishing attack. Vishing is voice-based, smishing is SMS-based, whaling targets executives.

---

**3.** An attacker exploits a window between when an application checks a file's permissions and when it actually reads the file. What vulnerability type is this?

A) Buffer Overflow  
B) Race Condition (TOCTOU)  
C) Memory Injection  
D) Directory Traversal

**Answer: B — Race Condition (TOCTOU).** Time-of-check to Time-of-use is the classic race condition vulnerability.

---

**4.** A threat hunter notices that user "jsmith" authenticated from Chicago at 8:00 AM and from Tokyo at 8:45 AM. What is this indicator called?

A) Concurrent session usage  
B) Out-of-cycle logging  
C) Impossible travel  
D) Credential replay

**Answer: C — Impossible travel.** Physical travel between those locations in 45 minutes is impossible, indicating compromised credentials being used from a remote location.

---

**5.** Malware is discovered that conceals itself by intercepting OS system calls and returning falsified results to hide its files and processes. What type of malware is this?

A) Keylogger  
B) Spyware  
C) Logic bomb  
D) Rootkit

**Answer: D — Rootkit.** Rootkits specifically hide themselves and other malware from the operating system.

---

**6.** A company cannot afford to replace all end-of-life workstations immediately. They implement additional monitoring and restrict network access for those workstations. This is an example of:

A) Risk avoidance  
B) Risk transfer  
C) Compensating controls  
D) Risk acceptance

**Answer: C — Compensating controls.** When the ideal mitigation (replacement) isn't feasible, compensating controls (monitoring + network restriction) are implemented.

---

**7.** An attacker intercepts a valid authentication session token and reuses it to access a web application. What attack is this?

A) Pass-the-Hash  
B) Replay attack  
C) Credential stuffing  
D) Brute force

**Answer: B — Replay attack.** The attacker captures and reuses a valid token without needing to know the original credentials.

---

**8.** Which technique allows an attacker to try one common password against thousands of accounts without triggering lockout policies?

A) Credential stuffing  
B) Rainbow table attack  
C) Password spraying  
D) Brute force

**Answer: C — Password spraying.** By trying one password per account across many accounts, the attacker stays below the lockout threshold.

---

**9.** A software vendor's build server is compromised, and malware is inserted into a software update that is then distributed to thousands of customers. What type of attack is this?

A) Zero-day exploit  
B) Supply chain attack  
C) Watering hole attack  
D) Malicious update via insider threat

**Answer: B — Supply chain attack** (specifically, a malicious update attack delivered via supply chain compromise). The SolarWinds attack is the defining real-world example.

---

**10.** Which of the following BEST mitigates the risk from an active brute-force attack against user accounts?

A) Password complexity requirements  
B) Account lockout policies  
C) MFA  
D) Password history requirements

**Answer: C — MFA.** Account lockout (B) helps against brute force but can cause DoS. Password complexity (A) slows brute force. But MFA (C) means even if the attacker guesses the correct password, they still can't authenticate without the second factor. MFA is the BEST mitigation.

---

# DOMAIN 3: SECURITY ARCHITECTURE
## Weight: 18% (~16 questions)

---

## 3.1 Architecture Models and Security Implications

### Cloud Architecture

**Cloud Service Models — The "as-a-Service" Spectrum:**

**IaaS (Infrastructure as a Service)** — Provider gives you raw compute, storage, and networking. You manage everything from the OS up. Example: AWS EC2, Azure VMs. Most control, most security responsibility on you.

**PaaS (Platform as a Service)** — Provider manages infrastructure and runtime. You manage your application and data. Example: AWS Elastic Beanstalk, Azure App Service. Split responsibility.

**SaaS (Software as a Service)** — Provider manages everything including the application. You just use it. Example: Microsoft 365, Salesforce, Google Workspace. Least control, provider manages most security.

**Shared Responsibility Matrix** — In cloud environments, security responsibilities are divided between the provider and the customer. What the provider secures vs. what you must secure depends on the service model. This is critical to understand — misunderstanding it leads to misconfigured cloud environments.

```
            | IaaS | PaaS | SaaS
------------|------|------|-----
Physical    | CSP  | CSP  | CSP
Hypervisor  | CSP  | CSP  | CSP
OS          | You  | CSP  | CSP
Middleware  | You  | CSP  | CSP
Application | You  | You  | CSP
Data        | You  | You  | You*
*Customer always responsible for data classification and access control
CSP = Cloud Service Provider
```

**Hybrid Considerations** — Combining on-premises and cloud resources. Security challenges: consistent policy enforcement across both environments, secure connectivity between them, identity management spanning both.

**Third-Party Vendors** — Cloud environments often involve numerous third-party services and APIs, each introducing supply chain risk.

### Modern Architecture Concepts

**Infrastructure as Code (IaC)** — Infrastructure is defined and managed using code (Terraform, CloudFormation). Benefits: consistency, version control, rapid deployment. Security implication: misconfigured IaC templates deploy insecure infrastructure at scale; code must be reviewed for security.

**Serverless** — Computing where the provider dynamically manages server allocation. Code runs in stateless functions (AWS Lambda, Azure Functions). Attack surface shifts to the application layer and permissions. No servers to patch.

**Microservices** — Application broken into small, independently deployable services that communicate via APIs. Security implication: each service-to-service communication is a potential attack vector; each microservice needs its own security controls; API security becomes critical.

**Software-Defined Networking (SDN)** — Network behavior defined by software rather than hardware configuration. Control plane and data plane are separated. Enables dynamic, programmable network segmentation. Security benefit: can rapidly reconfigure network in response to incidents.

**Containerization** — Packaging application code with its dependencies in a container (Docker). Containers share the host OS kernel. Lighter than VMs. Security: containers are isolated but not as isolated as VMs; container escape is analogous to VM escape; image security (scanning for vulnerable base images) is critical.

**Virtualization** — Running multiple virtual machines on one physical host. The hypervisor manages resource allocation.

### Special Environments

**IoT (Internet of Things)** — Embedded, networked devices: smart cameras, sensors, medical devices, industrial equipment. Security challenges: often have no security features, default credentials, can't be patched, run on legacy software, have a large attack surface due to quantity.

**ICS/SCADA (Industrial Control Systems / Supervisory Control and Data Acquisition)** — Control systems for critical infrastructure: power grids, water treatment, manufacturing. Characterized by: extreme availability requirements (can't just reboot), often decades old, designed for functionality not security, increasingly networked (and thus exposed).

**RTOS (Real-Time Operating System)** — An OS designed to process data within strict timing constraints. Used in embedded systems, medical devices, automotive. Security challenges: limited resources for security features, often lack encryption or authentication.

**Embedded Systems** — Computers built into hardware devices with a specific dedicated function. Examples: printers, routers, car ECUs. Often can't be patched.

**High Availability** — Systems designed to remain operational even when components fail.

### Architecture Considerations

When designing or evaluating security architecture, consider:
- **Availability** — Can the system tolerate failures?
- **Resilience** — How quickly does it recover?
- **Cost** — Budget constraints affect control selection
- **Responsiveness** — Security controls shouldn't degrade performance unacceptably
- **Scalability** — Can security scale with the system?
- **Ease of deployment** — Simple configurations are less error-prone
- **Risk transference** — Using cloud can transfer some risk to the provider
- **Ease of recovery** — Can you recover quickly from an incident?
- **Patch availability** — Can vulnerabilities be patched? (IoT often can't be)
- **Inability to patch** — OT/ICS/legacy systems
- **Power** — Redundant power for critical systems
- **Compute** — Encryption and monitoring consume resources

---

## 3.2 Secure Enterprise Infrastructure

### Infrastructure Considerations

**Device Placement** — Where you put a device in the network determines what traffic it sees and what it can inspect. A firewall between the internet and your network; an IDS on a mirror port to see all traffic; a web proxy between clients and the internet.

**Security Zones** — Logical or physical network segments with different trust levels:
- **Internet (untrusted zone)** — Public, assumed hostile
- **DMZ (Demilitarized Zone)** — Semi-trusted. Hosts public-facing services (web servers, email servers) that need to be accessible from the internet but shouldn't have direct access to the internal network.
- **Internal network (trusted zone)** — Corporate systems with more trust
- **Restricted zone** — Highly sensitive systems (finance, HR, executives), extra controls
- **OT/ICS zone** — Air-gapped or strictly isolated operational technology

**Attack Surface** — The sum of all paths an attacker could use to enter a system. Reduce it by: disabling unnecessary services, closing unused ports, removing unnecessary software, using least privilege.

**Failure Modes:**
- **Fail-open** — When a security device fails, traffic flows unimpeded. Prioritizes availability over security. Appropriate for systems where blocking all traffic on failure is unacceptable (some firewalls in medical environments).
- **Fail-closed (fail-secure)** — When a security device fails, all traffic is blocked. Prioritizes security over availability. Appropriate when unauthorized access is unacceptable.

**Device Attributes:**
- **Active** — Actively participates in traffic (inline). A firewall that blocks traffic is active.
- **Passive** — Monitors without participating. An IDS connected to a SPAN port is passive.
- **Inline** — Traffic flows through the device. The device can block traffic.
- **Tap/Monitor** — Device receives a copy of traffic. Can detect but not block.

### Network Appliances

**Jump Server (Bastion Host)** — A hardened server that acts as the only gateway to access a restricted network zone (like OT network or sensitive servers). All administrative access must go through the jump server, creating a chokepoint and audit trail.

**Proxy Server** — An intermediary between clients and servers. Benefits: caching, content filtering, hiding client IPs, SSL inspection. Forward proxy: client → proxy → internet. Reverse proxy: internet → proxy → internal server (load balancer, WAF).

**IDS (Intrusion Detection System)** — Monitors traffic and alerts on suspicious patterns. Passive — it does not block traffic. Like a security camera that records and alerts.

**IPS (Intrusion Prevention System)** — Same as IDS but inline — can block malicious traffic. Like a security guard that can physically stop someone.

**Load Balancer** — Distributes traffic across multiple servers for performance and availability. Also provides some security: hides individual server IPs, can block malformed requests.

**Sensors** — Passive monitoring devices that collect data for analysis.

### Port Security

**802.1X** — An IEEE standard for network access control. Devices must authenticate before being granted network access. The switch (or wireless AP) acts as an authenticator, passing credentials to a RADIUS server. Prevents unauthorized devices from plugging into network ports.

**EAP (Extensible Authentication Protocol)** — A flexible authentication framework used with 802.1X. Multiple EAP methods exist (EAP-TLS uses certificates, PEAP uses a password in a TLS tunnel).

### Firewall Types

**Packet Filtering Firewall** — Inspects IP and TCP/UDP headers only. Makes decisions based on IP address, port, protocol. Stateless — doesn't track connections. Fast but limited.

**Stateful Firewall (Layer 4)** — Tracks the state of network connections. Knows that a TCP packet is part of an established connection vs. a new connection attempt. More secure than packet filtering.

**Next-Generation Firewall (NGFW)** — Combines stateful inspection with application awareness (Layer 7 inspection), user identity, intrusion prevention, URL filtering, and SSL inspection. Can identify the application regardless of port (identify Skype on port 443).

**Web Application Firewall (WAF)** — Specifically designed to protect web applications. Understands HTTP and filters based on application-layer content. Defends against SQLi, XSS, CSRF, directory traversal.

**Unified Threat Management (UTM)** — An all-in-one security appliance combining firewall, IDS/IPS, antivirus, content filtering, VPN, spam filtering. Common in SMB environments.

**Layer 4 vs Layer 7:**
- Layer 4: makes decisions based on ports and connection state
- Layer 7: understands application protocols; much more granular inspection

### Secure Communication and Access

**VPN (Virtual Private Network)** — Creates an encrypted tunnel over a public network (internet). Types:
- **Remote access VPN** — Individual user connects to the corporate network
- **Site-to-site VPN** — Connects two entire networks (branch to HQ)

**Tunneling Protocols:**
- **TLS** — Encrypts application-layer data. HTTPS is HTTP over TLS. Used for remote access VPNs.
- **IPSec** — Encrypts at the IP layer. Used for site-to-site VPNs. Modes:
  - **Transport mode** — Encrypts only the payload
  - **Tunnel mode** — Encrypts the entire original IP packet (encapsulates it in a new IP packet)
  - **AH (Authentication Header)** — Provides integrity and authentication but NOT confidentiality
  - **ESP (Encapsulating Security Payload)** — Provides confidentiality, integrity, and authentication

**SD-WAN (Software-Defined Wide Area Network)** — Uses software to manage and optimize WAN connections across multiple links (MPLS, broadband, cellular). More flexible and cost-effective than traditional WAN. Security consideration: traffic flowing outside traditional network boundaries needs consistent policy enforcement.

**SASE (Secure Access Service Edge)** — Converges networking (SD-WAN) and security (firewall, CASB, Zero Trust) into a cloud-delivered service model. Security enforced at the edge, regardless of where users or resources are. Appropriate for distributed workforces.

---

## 3.3 Protecting Data

### Data Types

- **Regulated data** — Subject to legal/regulatory requirements: PII (GDPR), PHI (HIPAA), PCI data (PCI DSS), student records (FERPA)
- **Trade secrets** — Proprietary business information (formulas, processes)
- **Intellectual property** — Copyrights, patents, trademarks
- **Legal information** — Attorney-client privileged, litigation holds
- **Financial information** — Earnings, projections, personal financial data
- **Human-readable** — Text, documents, data people can read
- **Non-human-readable** — Binary, encoded data requiring tools to interpret

### Data Classifications

Standard classification levels (government and corporate may differ):
- **Public** — Can be disclosed to anyone; no protection required
- **Private / Internal** — Not for public release but not highly sensitive
- **Sensitive / Confidential** — Limited distribution; requires protection
- **Restricted / Critical** — Highest protection; severely limited access

### Data States

**Data at Rest** — Stored on media (hard drive, SSD, tape, USB). Protection: full-disk encryption (FDE), file-level encryption, access controls.

**Data in Transit** — Moving across a network. Protection: TLS, HTTPS, VPN, IPSec, SSH.

**Data in Use** — Currently being processed in CPU and RAM. Hardest to protect. Protection: secure enclaves, memory encryption.

**Data Sovereignty** — Data is subject to the laws of the country where it is physically stored. Storing EU citizen data in the US creates GDPR compliance obligations in addition to US law.

**Geolocation** — Data location can be tracked and used to enforce policy (geographic restrictions on who can access data).

### Methods to Secure Data

- **Geographic restrictions** — Limit access based on physical location
- **Encryption** — Make data unreadable without the key
- **Hashing** — Verify integrity
- **Masking** — Replace real data with fake data
- **Tokenization** — Replace sensitive data with tokens
- **Obfuscation** — Make data harder to understand
- **Segmentation** — Separate data stores for different classification levels
- **Permission restrictions** — Enforce least privilege

---

## 3.4 Resilience and Recovery

### High Availability

**Load Balancing** — Distributes traffic across multiple servers. If one server fails, others handle the load. Types: active-active (all servers handle traffic) vs. active-passive (standby takes over on failure).

**Clustering** — Multiple servers work together as one logical system. Provides failover if one node fails.

### Recovery Sites

When disaster strikes, you need somewhere to operate:

**Hot Site** — Fully operational duplicate of the primary site. Systems are running and data is synchronized. Recovery time: minutes to hours. Most expensive.

**Warm Site** — Has hardware and infrastructure but needs data restored and systems configured. Recovery time: hours to days.

**Cold Site** — Just physical space and basic utilities. No equipment. You must bring everything. Recovery time: days to weeks. Least expensive.

**Geographic Dispersion** — Recovery sites must be far enough from the primary site to not be affected by the same regional disaster.

### Continuity Planning

**Platform Diversity** — Using different hardware/software vendors reduces the risk that a single vulnerability or vendor failure takes everything down.

**Multi-Cloud** — Using multiple cloud providers for resilience. If one provider has an outage, services can run on another.

**Continuity of Operations** — Planning to maintain essential business functions during and after a disruption.

**Capacity Planning** — Ensuring you have enough resources (people, technology, infrastructure) to handle operations including failure scenarios.

### Testing Resilience

**Tabletop Exercise** — Discussion-based scenario walkthrough with stakeholders. No actual systems involved. Used to identify gaps in procedures.

**Failover** — Actually switching to the backup system to test it works.

**Simulation** — Simulating a disaster scenario in a more realistic way than tabletop.

**Parallel Processing** — Running primary and secondary systems simultaneously to verify the backup works before cutting over.

### Backups

**Onsite vs. Offsite** — Onsite is fast to restore from; offsite protects against local disasters. The 3-2-1 rule: 3 copies, 2 different media types, 1 offsite.

**Frequency** — How often backups are taken determines RPO (how much data can be lost).

**Backup types:**
- **Full** — Complete backup of all data. Slow to create, fast to restore.
- **Incremental** — Only changes since last backup. Fast to create, slow to restore (need all incrementals).
- **Differential** — Changes since last full backup. Moderate create time, faster restore than incremental.

**Encryption** — Backups must be encrypted. An unencrypted backup of sensitive data is as dangerous as the original.

**Snapshots** — Point-in-time copies of a system state. Fast to create and restore in virtualized environments.

**Replication** — Continuously copying data to another location. Near-real-time recovery possible.

**Journaling** — Keeping a log of all changes to data. Allows recovery to any specific point in time.

### Power Resilience

**UPS (Uninterruptible Power Supply)** — Battery backup that provides power during brief outages and clean shutdown during extended outages.

**Generators** — Provides extended backup power during long outages. Requires fuel supply and regular testing.

---

## Domain 3 Practice Questions

**1.** A financial company wants to host public-facing web servers that must communicate with internal databases, while preventing direct internet access to internal systems. What architecture element BEST accomplishes this?

A) VPN  
B) DMZ  
C) NAT  
D) VLAN

**Answer: B — DMZ.** The Demilitarized Zone places web servers where they can be accessed from the internet while being separated from the internal network containing databases.

---

**2.** An organization discovers that their cloud provider experienced an outage that made their critical application unavailable. The organization had not implemented any redundancy. Which recovery strategy would have BEST prevented this?

A) Hot site  
B) Warm site  
C) Multi-cloud  
D) Cold site

**Answer: C — Multi-cloud.** The organization needs redundancy across providers. Multi-cloud means if one provider goes down, services run on another.

---

**3.** A security control fails and all traffic is blocked. What is this failure mode called?

A) Fail-open  
B) Fail-safe  
C) Fail-closed  
D) Active failure

**Answer: C — Fail-closed.** When the device fails, traffic is blocked (the "closed" position). This prioritizes security over availability.

---

**4.** An IPS is deployed inline on a network. Which of the following is the PRIMARY capability that distinguishes it from an IDS?

A) It can detect anomalies  
B) It can block malicious traffic  
C) It uses signature-based detection  
D) It monitors all network traffic

**Answer: B — It can block malicious traffic.** Both IDS and IPS detect; the critical difference is that the IPS is inline and can actively block. An IDS is passive/monitoring only.

---

**5.** A company is migrating to AWS and wants to use virtual machines where they manage the OS, middleware, and applications. Which cloud service model is this?

A) SaaS  
B) PaaS  
C) IaaS  
D) FaaS

**Answer: C — IaaS.** In IaaS, the provider gives you virtual machines; you manage everything from the OS up.

---

**6.** Which tunneling protocol encrypts data at the IP layer and can operate in either transport mode (encrypting only payload) or tunnel mode (encrypting the entire original packet)?

A) TLS  
B) SSL  
C) IPSec  
D) SSH

**Answer: C — IPSec.** IPSec operates at Layer 3 and has both transport and tunnel modes. TLS operates at Layer 4+.

---

**7.** Which backup strategy creates the fastest backups but requires the most time to restore?

A) Full  
B) Differential  
C) Incremental  
D) Snapshot

**Answer: C — Incremental.** Incrementals are fastest to create (only changes since last backup) but to restore you need the last full backup plus every subsequent incremental in order.

---

---

# DOMAIN 4: SECURITY OPERATIONS
## Weight: 28% (~25 questions) — The Biggest Domain

---

## 4.1 Security Techniques for Computing Resources

### Secure Baselines

A **baseline** is a known-good, approved security configuration for a system.

- **Establish** — Define what the baseline is (using CIS Benchmarks, STIG, vendor guides)
- **Deploy** — Apply the baseline configuration to all systems (using GPO, MDM, configuration management tools like Ansible)
- **Maintain** — Monitor for deviation from baseline and correct it (configuration drift)

### Hardening Targets

Different systems have different hardening priorities:

**Mobile devices** — MDM enrollment, screen lock, remote wipe capability, encryption, app management

**Workstations** — Disable unnecessary services, endpoint protection, host firewall, screen lock, patch management, standard user accounts (no admin for daily use)

**Switches** — Disable unused ports, disable Telnet (use SSH), enable 802.1X, VLAN segmentation, change default credentials, disable CDP/LLDP on external ports

**Routers** — Disable unused protocols, access control lists, route filtering, encrypted management (SSH not Telnet), change defaults

**Cloud infrastructure** — Follow CSP security benchmarks, use IAM roles (not root accounts), enable logging, use security groups, encrypt data

**Servers** — Minimal installed software, disable unnecessary services, regular patching, host firewall, enable auditing, strong authentication

**ICS/SCADA** — Segment from corporate network (or air-gap), application whitelist, disable internet access, strict change control

**Embedded systems/RTOS/IoT** — Change default passwords, disable unused features, keep firmware updated, network segmentation

### Wireless Security

**Site Survey** — Physical assessment of an area to determine optimal AP placement, coverage, interference, and security considerations.

**Heat Maps** — Visual representation of wireless signal coverage across a physical space. Used to identify coverage gaps and overlapping zones.

### Mobile Solutions

**MDM (Mobile Device Management)** — Centralized management of mobile devices. Can enforce policies, push configurations, deploy apps, remotely wipe devices.

**Deployment Models:**
- **BYOD (Bring Your Own Device)** — Employee uses personal device for work. Lowest cost; highest risk (employer has limited control). MDM profiles separate work/personal data.
- **COPE (Corporate-Owned, Personally Enabled)** — Company owns the device but allows personal use. More control than BYOD.
- **CYOD (Choose Your Own Device)** — Employee chooses from a list of approved devices. Company owns it.

**Connection Methods:**
- **Cellular** — 4G/5G networks. Encrypted by carrier. Not controlled by the organization directly.
- **Wi-Fi** — Requires secure Wi-Fi implementation. 
- **Bluetooth** — Short range. Potential for BlueSnarfing, Bluebugging. Should be disabled when not in use.

### Wireless Security Settings

**WPA3 (Wi-Fi Protected Access 3)** — Current wireless security standard. Improvements over WPA2:
- **SAE (Simultaneous Authentication of Equals)** — Replaces PSK; more resistant to offline dictionary attacks
- **Individual data encryption** — Each session uses unique encryption keys even on open networks
- **Forward secrecy** — Compromising one session key doesn't expose other sessions

**RADIUS (Remote Authentication Dial-In User Service)** — Network protocol for centralized AAA for network access. Used with 802.1X for enterprise wireless authentication. Users authenticate against a central server rather than using a shared PSK.

**Cryptographic protocols** for wireless: CCMP (Counter Mode/CBC-MAC Protocol) used with WPA2/WPA3; TKIP (deprecated, used with old WPA).

**Authentication protocols:** EAP-TLS (certificate-based, strongest), PEAP (password in TLS tunnel), EAP-TTLS.

### Application Security

**Input Validation** — Checking all user input for type, length, format, and range before processing. The primary defense against injection attacks (SQLi, XSS, command injection). Never trust user input.

**Secure Cookies:**
- **HttpOnly flag** — Cookie cannot be accessed by JavaScript (prevents XSS cookie theft)
- **Secure flag** — Cookie only sent over HTTPS
- **SameSite attribute** — Prevents cross-site request forgery by controlling when cookies are sent with cross-origin requests

**Static Code Analysis** — Analyzing source code without executing it to find vulnerabilities. Performed during development. Tools: Checkmarx, SonarQube, Semgrep.

**Dynamic Analysis (DAST)** — Testing a running application for vulnerabilities. Sends malformed inputs and observes behavior. Tools: Burp Suite, OWASP ZAP.

**Code Signing** — Software is cryptographically signed by the developer. Users and operating systems can verify the software is authentic and hasn't been modified. Prevents tampering in distribution.

**Sandboxing** — Running suspicious code in an isolated environment to observe behavior without risk to the real system. Used in malware analysis and as a security feature in browsers and OS.

---

## 4.2 Asset Management

**Acquisition/Procurement** — Security requirements should be defined before purchasing hardware and software. Vendor security assessments, supply chain verification.

**Assignment/Accounting:**
- **Ownership** — Every asset must have an identified owner responsible for its security
- **Classification** — Every asset must be classified by sensitivity and value

**Monitoring/Asset Tracking:**
- **Inventory** — Complete, accurate list of all hardware and software assets
- **Enumeration** — Discovery and listing of assets (often automated)

**Disposal/Decommissioning:**
- **Sanitization** — Removing data from media before repurposing or discarding. Methods: overwriting (DoD 5220.22-M standard: 3-7 passes), cryptographic erasure (delete the encryption key, making data unrecoverable)
- **Destruction** — Physical destruction for highly sensitive data: shredding, degaussing (magnetic field), incineration
- **Certification** — Documented proof of destruction, often required for compliance
- **Data Retention** — Keeping data for the legally required period before destruction

---

## 4.3 Vulnerability Management

### Identification Methods

**Vulnerability Scanner** — Automated tool that identifies known vulnerabilities in systems. Examples: Nessus, Qualys, OpenVAS. Produces a list of CVEs with severity scores.

**Application Security Testing:**
- **Static Analysis (SAST)** — Scans source code
- **Dynamic Analysis (DAST)** — Tests running application
- **Package Monitoring** — Checking third-party libraries for known vulnerabilities (SCA - Software Composition Analysis)

**Threat Feed** — Real-time intelligence about active threats. Sources:
- **OSINT (Open-Source Intelligence)** — Publicly available information (CVE databases, security blogs, threat actor reports)
- **Proprietary/Third-Party** — Commercial threat intelligence services
- **Information-Sharing Organizations** — ISACs (Information Sharing and Analysis Centers), government sharing (CISA, FBI)
- **Dark Web** — Monitoring dark web for leaked credentials, discussion of your organization

**Penetration Testing** — Authorized, simulated attack to test security controls. Finds vulnerabilities that automated scanners miss. (Covered in depth in Domain 5.)

**Responsible Disclosure / Bug Bounty** — Security researchers find and report vulnerabilities to the vendor. Bug bounty programs pay researchers for valid findings.

**System/Process Audit** — Reviews configuration, procedures, and controls for compliance with policy.

### Analysis

**False Positive** — Scanner reports a vulnerability that doesn't actually exist. Must be investigated and confirmed or dismissed.

**False Negative** — A real vulnerability exists but the scanner doesn't find it. More dangerous than false positives.

**Prioritization** — Not all vulnerabilities can be patched immediately. Prioritize based on:

**CVSS (Common Vulnerability Scoring System)** — Standardized 0–10 score for vulnerability severity. Components: base score (severity of the vuln itself), temporal score (patch availability, exploit maturity), environmental score (your environment's exposure).
- 9.0–10.0: Critical
- 7.0–8.9: High  
- 4.0–6.9: Medium
- 0.1–3.9: Low

**CVE (Common Vulnerabilities and Exposures)** — Standardized identifier for publicly known vulnerabilities. Format: CVE-YEAR-NUMBER. Example: CVE-2017-0144 (EternalBlue). The CVE list is maintained by MITRE.

**Vulnerability Classification** — Categorizing vulnerabilities by type (injection, buffer overflow, etc.)

**Exposure Factor** — The percentage of an asset's value likely to be lost in an incident.

**Environmental Variables** — How critical is this system to your organization? Is it internet-facing? What compensating controls exist?

**Industry/Organizational Impact** — What's the business impact if this vulnerability is exploited?

**Risk Tolerance** — How much risk is the organization willing to accept?

### Vulnerability Response

**Patching** — Apply the vendor's security patch. The primary remediation.

**Insurance** — Transfer risk through cyber insurance. Not a technical remediation.

**Segmentation** — Isolate the vulnerable system to limit exposure.

**Compensating controls** — Additional controls when direct remediation isn't possible.

**Exceptions and Exemptions** — Formally documented decisions not to remediate a vulnerability, with justification, risk acceptance, and expiration date.

### Validation of Remediation

**Rescanning** — Run the vulnerability scanner again after patching to confirm the vulnerability is gone.

**Audit** — Formal review of the remediation process and outcome.

**Verification** — Independently confirm the fix is effective.

---

## 4.4 Security Alerting and Monitoring

### Monitoring Computing Resources

Monitor at all levels:
- **Systems** — OS metrics, patch status, security events
- **Applications** — Application logs, errors, performance
- **Infrastructure** — Network devices, cloud resources, storage

### Monitoring Activities

**Log Aggregation** — Collecting logs from all sources into a central repository for analysis.

**Alerting** — Generating notifications when suspicious conditions are detected.

**Scanning** — Active probing of systems to identify vulnerabilities or verify configurations.

**Reporting** — Producing regular summaries of security posture for stakeholders.

**Archiving** — Retaining logs for compliance and forensic purposes.

**Alert Response and Remediation:**
- **Quarantine** — Isolating a suspicious system to prevent spread while investigation occurs
- **Alert Tuning** — Adjusting detection rules to reduce false positives without missing real threats

### Tools

**SCAP (Security Content Automation Protocol)** — Standardized approach to automating vulnerability management and security policy compliance. Includes CVE, CVSS, OVAL (machine-readable vuln descriptions).

**Benchmarks** — Configuration standards (CIS Benchmarks, STIGs) used to measure system hardening.

**Agents vs. Agentless:**
- **Agent-based** — Software installed on each monitored system. More visibility into the host. Requires management of the agent.
- **Agentless** — Monitoring done remotely via protocols like SNMP, WMI, SSH. Simpler to deploy, less visibility.

**SIEM (Security Information and Event Management)** — Collects, correlates, and analyzes log data from across the environment. Provides centralized visibility, alerting, and compliance reporting. Examples: Splunk, Microsoft Sentinel, IBM QRadar, Elastic SIEM.

**Antivirus** — Signature-based and heuristic detection of known malware. Baseline endpoint security.

**DLP (Data Loss Prevention)** — Monitors and blocks unauthorized transfer of sensitive data. Inspects content of emails, files, and network traffic for sensitive patterns (PII, credit card numbers).

**SNMP Traps** — Unsolicited notifications sent from network devices to the management system when specific events occur (interface down, high CPU, etc.).

**NetFlow** — Network telemetry data from routers and switches. Provides traffic flow information without full packet capture. Used for bandwidth analysis, anomaly detection, and forensics.

**Vulnerability Scanners** — (see 4.3)

---

## 4.5 Enterprise Security Capabilities (Enhancing Security)

### Firewall Management

**Rules** — Define what traffic is allowed or denied. Order matters — rules are processed top-down; first match wins.

**Access Lists** — Permit or deny traffic based on source/destination IP, port, protocol.

**Ports/Protocols** — Firewalls can restrict traffic based on port numbers and protocols.

**Screened Subnets** — Creating a DMZ using two firewalls (outer firewall between internet and DMZ, inner firewall between DMZ and internal network).

### IDS/IPS Management

**Trends** — Behavioral/anomaly-based detection looks for deviations from established baselines.

**Signatures** — Pattern-based detection. Matches traffic against known attack signatures. Fast but misses zero-days and novel attacks.

### Web Filter

**Agent-based** — Software on endpoints enforces web filtering locally.

**Centralized proxy** — All web traffic routed through a proxy that applies filtering.

**URL Scanning** — Checks URLs against databases of malicious or policy-violating sites.

**Content Categorization** — Classifying websites by content type (social media, gambling, adult content, malware distribution).

**Block Rules** — Specific URLs or categories blocked.

**Reputation** — Blocking sites with poor security reputation scores.

### Operating System Security

**Group Policy (GPO)** — Windows tool for enforcing configuration settings across a domain. Can enforce password policies, disable USB, restrict software, configure firewall.

**SELinux (Security-Enhanced Linux)** — Mandatory Access Control implementation for Linux. Enforces policies even for root processes. Very granular control.

### Secure Protocol Implementation

**Protocol Selection** — Choose encrypted protocols over plaintext equivalents:
- SSH instead of Telnet
- HTTPS instead of HTTP
- SFTP/FTPS instead of FTP
- LDAPS instead of LDAP
- SNMPv3 instead of SNMPv1/v2

**Port Selection** — Use standard secure ports; avoid running services on non-standard ports as a security measure (security through obscurity alone is insufficient).

**Transport Method** — Ensure data in transit is encrypted (TLS, IPSec).

### DNS Filtering

Blocking malicious or policy-violating domains at the DNS level before connections are made. Examples: Cisco Umbrella, Pi-hole. Effective against C2 traffic (many malware families use domain-based C2).

### Email Security

**SPF (Sender Policy Framework)** — DNS TXT record listing which mail servers are authorized to send email for your domain. Receiving servers check SPF to detect spoofed senders.

**DKIM (DomainKeys Identified Mail)** — Cryptographic signature added to outgoing email. Receiving servers verify the signature using the sender's public key from DNS. Proves the email wasn't modified in transit.

**DMARC (Domain-based Message Authentication, Reporting & Conformance)** — Builds on SPF and DKIM. Allows domain owners to specify what receiving servers should do with email that fails SPF/DKIM checks (none, quarantine, reject) and receive reports about failures.

**Email Gateway** — An email security appliance or service that inspects inbound and outbound email for malware, spam, phishing, and data exfiltration.

> **Memory aid:** SPF = who can send | DKIM = message wasn't tampered | DMARC = what to do when SPF/DKIM fail

### File Integrity Monitoring (FIM)

Creates cryptographic hashes of files and monitors for changes. Alert when system files, configuration files, or critical data is modified without authorization. Example tools: Tripwire, OSSEC.

### DLP (Data Loss Prevention)

Monitors and prevents unauthorized transfer of sensitive data. Implementations:
- Network DLP — Inspects traffic at the network level
- Endpoint DLP — Agent on endpoints monitors file operations
- Cloud DLP — Monitors cloud storage and services

### NAC (Network Access Control)

Controls which devices are allowed to connect to the network. Checks device compliance (patch level, AV installed, encryption enabled) before granting access. Non-compliant devices are quarantined or given limited access.

### EDR and XDR

**EDR (Endpoint Detection and Response)** — Next-generation endpoint security that records endpoint activity, detects threats based on behavior (not just signatures), and provides tools for investigation and response. Examples: CrowdStrike Falcon, SentinelOne, Microsoft Defender for Endpoint.

**XDR (Extended Detection and Response)** — Extends EDR across multiple security domains: endpoints, network, cloud, email. Correlates signals from multiple sources for improved detection and investigation.

### User Behavior Analytics (UBA/UEBA)

Establishes a baseline of normal user behavior, then alerts on deviations. Detects: insider threats, compromised accounts, privilege escalation. Uses machine learning. Example: user who normally downloads 50 MB/day suddenly downloads 50 GB.

---

## 4.6 Identity and Access Management (IAM)

### User Account Lifecycle

**Provisioning** — Creating user accounts with appropriate access when someone joins. Must follow the principle of least privilege from day one.

**De-provisioning** — Removing access when someone leaves or changes roles. Critical: former employees with active accounts are a common security issue. Should be immediate upon termination.

**Permission Assignments** — What specific access rights does the account have? Should be documented, approved, and reviewed regularly.

**Identity Proofing** — Verifying someone's identity before creating their account or granting access. Prevents account creation for non-existent people.

### Federation and SSO

**Federation** — Linking identity across multiple systems or organizations. A user's identity in one organization can be trusted by another organization's systems.

**SSO (Single Sign-On)** — User authenticates once and gains access to multiple systems without re-authenticating. Benefits: better user experience, centralized policy enforcement. Risk: if SSO credentials are compromised, all connected systems are at risk.

**SSO Technologies:**
- **LDAP (Lightweight Directory Access Protocol)** — Protocol for accessing and maintaining directory information. Active Directory uses LDAP. Used for internal SSO.
- **OAuth 2.0** — Authorization framework (not authentication). Allows a third-party app to access resources on behalf of a user without sharing credentials. "Login with Google" uses OAuth.
- **SAML (Security Assertion Markup Language)** — XML-based standard for exchanging authentication and authorization data. Used for enterprise federation and web SSO. IdP (Identity Provider) authenticates and sends assertions to SP (Service Provider).

**Interoperability** — Federated systems must agree on a common protocol (SAML, OAuth, OpenID Connect) to share identity information.

**Attestation** — Formal certification that access rights are appropriate. Users and managers periodically certify that accounts have the right permissions.

### Access Control Models

**MAC (Mandatory Access Control)** — Access decisions are made by the system based on security labels/classifications. Users and resource owners cannot override these rules. Used in highly secure government environments. SELinux implements MAC.

**DAC (Discretionary Access Control)** — Resource owners decide who gets access. Standard Windows/Linux file permissions (owner sets read/write/execute for others). Most flexible but least secure.

**RBAC (Role-Based Access Control)** — Access based on job role. Assign users to roles; roles have permissions. When someone changes jobs, change their role. Most common model in enterprise.

**Rule-Based Access Control** — Access determined by a set of rules independent of user identity. Time-of-day restrictions, IP-based rules. Firewall ACLs are rule-based.

**ABAC (Attribute-Based Access Control)** — Most flexible and fine-grained. Access decisions based on attributes of the user, resource, and environment. Example: "Allow access if user.department='Finance' AND resource.classification='Financial' AND environment.time is BusinessHours."

**Time-of-day restrictions** — Access only permitted during specific hours. Example: system accessible 8 AM–6 PM only.

**Least Privilege** — Grant only the minimum permissions needed to perform the job function. Reviewed regularly.

### MFA (Multi-Factor Authentication)

Requires two or more factors from different categories:

**Factors:**
- **Something you know** — Password, PIN, security question answer
- **Something you have** — Smart card, hardware token (RSA SecurID), authenticator app (TOTP), SMS code
- **Something you are** — Biometrics: fingerprint, face, iris, voice
- **Somewhere you are** — Geolocation-based (you must be in a specific location)

**Implementations:**
- **Biometrics** — Fingerprint readers, facial recognition, iris scanners. Convenient, but false acceptance/rejection rates matter. Cannot be changed if compromised.
- **Hard tokens** — Physical devices that generate one-time passwords (HOTP - HMAC-based OTP, or TOTP - Time-based OTP)
- **Soft tokens** — Authenticator apps (Google Authenticator, Microsoft Authenticator) on smartphones generating TOTP
- **Security keys** — FIDO2/WebAuthn hardware keys (YubiKey). Phishing-resistant because they verify the site origin.

### Password Concepts

**Best Practices:**
- **Length** — Longer is better. 14+ characters. A long passphrase beats a complex short password.
- **Complexity** — Mix of uppercase, lowercase, numbers, symbols. But prioritize length.
- **Reuse** — Never reuse passwords across sites/accounts. Password history enforcement prevents reuse.
- **Expiration** — NIST now recommends against mandatory regular expiration unless there's a known compromise; forcing frequent changes leads to weak, predictable passwords.
- **Age** — Minimum age prevents users from immediately changing back to their old password.

**Password Managers** — Applications that store and generate strong, unique passwords. Single master password protects all others. Acceptable risk trade-off for practical security.

**Passwordless** — Authentication without a password. Uses biometrics, FIDO2 keys, or magic links. Eliminates password-based attacks entirely.

### Privileged Access Management (PAM)

**Just-In-Time (JIT) Permissions** — Administrative access is granted only when needed and automatically revoked after a time period. Reduces exposure of privileged accounts.

**Password Vaulting** — Storing privileged credentials in a secure vault. Users check out credentials when needed; credentials can be rotated automatically. Examples: CyberArk, HashiCorp Vault.

**Ephemeral Credentials** — Short-lived credentials that expire quickly and are auto-generated. An ephemeral certificate for SSH might be valid for only 4 hours.

---

## 4.7 Automation and Orchestration

### Use Cases

**User Provisioning** — Automated account creation and access assignment when someone joins, based on HR system triggers.

**Resource Provisioning** — Automatically deploying cloud resources when needed.

**Guard Rails** — Automated policy enforcement that prevents certain actions (e.g., automatic blocking of misconfigured cloud storage buckets).

**Security Groups** — Automated management of access group membership.

**Ticket Creation** — Automated creation of service desk tickets when security events are detected.

**Escalation** — Automatically escalating alerts that aren't acknowledged within a time window.

**Enabling/Disabling Services and Access** — Automated account disabling upon termination.

**Continuous Integration and Testing** — Automated security testing as part of the software build pipeline (DevSecOps).

**APIs** — Integration between security tools via APIs enables automation and data sharing.

### Benefits of Automation

- **Efficiency/Time saving** — Faster than manual processes
- **Enforcing baselines** — Configuration always matches policy
- **Standard infrastructure** — Consistent, reproducible deployments
- **Scaling securely** — Security scales with the environment
- **Employee retention** — Automate repetitive tasks; humans work on interesting problems
- **Reaction time** — Automated responses are faster than human responses
- **Workforce multiplier** — Small security team can manage large environments

### Considerations

- **Complexity** — Automated systems are harder to understand and troubleshoot
- **Cost** — Development and maintenance costs
- **Single point of failure** — If the automation system fails, what happens?
- **Technical debt** — Automated scripts and workflows require maintenance
- **Ongoing supportability** — Who maintains the automation when the person who built it leaves?

---

## 4.8 Incident Response

### The IR Process (PICERL)

Memorize this order — the exam will test you on it:

1. **Preparation** — Before an incident: IR plan, playbooks, trained team, tools in place, communication channels established, tabletop exercises
2. **Detection** — Identifying that an incident has occurred (SIEM alerts, user reports, threat intel)
3. **Analysis** — Determining the scope, nature, and impact of the incident. Is this a real incident or a false positive?
4. **Containment** — Stopping the spread. Short-term containment (isolate affected system) and long-term containment (rebuild or patch).
5. **Eradication** — Removing the threat: deleting malware, revoking compromised credentials, removing persistence mechanisms
6. **Recovery** — Restoring affected systems to normal operation. Verify they are clean before returning to production.
7. **Lessons Learned (Post-Incident Activity)** — Documenting what happened, what worked, what didn't, how to improve. Update IR plans and playbooks.

> **Exam Tip:** The most common exam trick: what do you do FIRST? If you suspect a breach, first **detect/identify** (confirm it's real), then **contain** (stop the bleeding) — NOT eradicate. Many students want to "remove the malware first" — but you must preserve evidence and contain first.

### IR Training and Testing

**Tabletop Exercise** — Discussion-based walkthrough of an incident scenario. All key stakeholders participate. Identifies gaps in communication, decision-making, and procedures. No actual systems involved.

**Simulation** — More realistic than tabletop. Actually simulates specific aspects of an incident. May involve systems.

### Root Cause Analysis (RCA)

After containment and recovery, determine the underlying cause of the incident to prevent recurrence. Not just "what happened" but "why did it happen and what process/control failed?"

### Threat Hunting

Proactively searching through networks and endpoints to find threats that evaded existing detection. Hypothesis-driven: "Assume breach and look for evidence." Uses: threat intelligence, behavioral analysis, anomaly detection.

### Digital Forensics

**Legal Hold** — Preserving all potentially relevant evidence in anticipation of litigation or investigation. Stop deleting or modifying data once a legal hold is issued.

**Chain of Custody** — Documented record of who handled evidence and when. Critical for evidence admissibility in court. Every person who touches evidence must be documented.

**Acquisition** — Creating a forensic copy of evidence (disk image, memory dump). The original must be preserved intact. Work only on the copy.

**Preservation** — Maintaining evidence integrity. Use write blockers when imaging drives. Hash the evidence before and after to prove no changes occurred.

**Reporting** — Formal documentation of findings, methodology, and conclusions. Must be objective, reproducible, and defensible.

**E-discovery** — The process of identifying, preserving, collecting, and producing electronically stored information (ESI) in response to legal requests.

---

## 4.9 Data Sources for Investigation

### Log Types

**Firewall Logs** — What traffic was allowed or denied. Source/destination IPs, ports, timestamps.

**Application Logs** — Errors, events, user actions within applications.

**Endpoint Logs** — Windows Event Logs, macOS/Linux system logs. Process creation, logon events, file access.

**OS-Specific Security Logs:**
- Windows Security Event Log: Event IDs to know:
  - 4624: Successful logon
  - 4625: Failed logon
  - 4648: Logon with explicit credentials
  - 4672: Privileged logon (admin)
  - 4688: New process created
  - 4698: Scheduled task created

**IPS/IDS Logs** — Triggered signatures, blocked connections.

**Network Logs** — Flow data (NetFlow), DHCP logs (IP-to-MAC mapping at a point in time), DNS logs.

**Metadata** — Data about data. File metadata: creation time, modification time, author. Email metadata: sender IP, server hops.

### Data Sources for Investigation

- **Vulnerability Scans** — Historical scan data shows what vulnerabilities existed at time of compromise
- **Automated Reports** — Regular security posture reports
- **Dashboards** — Real-time visibility into security metrics
- **Packet Captures (PCAP)** — Full packet data for network forensics

---

## Domain 4 Practice Questions

**1.** An analyst receives an alert that a workstation is communicating with a known malware C2 server. What should the analyst do FIRST?

A) Wipe and reimage the workstation  
B) Run antivirus on the workstation  
C) Isolate/contain the workstation from the network  
D) Notify law enforcement

**Answer: C — Contain/isolate.** The immediate priority is preventing lateral movement and further damage. Evidence must be preserved. After containment: analysis, then eradication. Reimaging (A) destroys evidence.

---

**2.** Which access control model is BEST suited for a government environment where users cannot override access decisions and data is labeled with classification levels?

A) DAC  
B) RBAC  
C) MAC  
D) ABAC

**Answer: C — MAC (Mandatory Access Control).** MAC uses labels and classifications enforced by the system. Users and even resource owners cannot override. DAC lets owners decide; RBAC is role-based.

---

**3.** An employee leaves the company on Friday. Which action is MOST critical from a security perspective?

A) Recovering their equipment on Monday  
B) Immediately disabling their accounts and revoking access  
C) Forwarding their email to their manager  
D) Changing their password

**Answer: B — Immediately disabling accounts and revoking access.** Former employee accounts are a significant risk. This must happen at or before the moment of departure, not afterward.

---

**4.** Which email authentication mechanism allows a domain owner to specify what action receiving mail servers should take when an email fails SPF or DKIM verification?

A) SPF  
B) DKIM  
C) DMARC  
D) S/MIME

**Answer: C — DMARC.** DMARC ties SPF and DKIM together and lets the sending domain specify a policy: none, quarantine, or reject for failing messages.

---

**5.** A company wants to ensure that administrative access to servers is only granted for the duration of a specific task and is automatically revoked afterward. What PAM feature is this?

A) Password vaulting  
B) Ephemeral credentials  
C) Just-in-time permissions  
D) Role-based access

**Answer: C — Just-in-time (JIT) permissions.** JIT grants elevated access only when needed and removes it when the task is complete.

---

**6.** An analyst discovers that the logs for a critical server are missing for the 3-hour window when a suspected breach occurred. This is classified as which type of indicator?

A) Out-of-cycle logging  
B) Resource inaccessibility  
C) Missing logs  
D) Concurrent session usage

**Answer: C — Missing logs.** Gaps in logging are a key indicator that either logging failed (configuration issue) or an attacker deliberately cleared or disabled logging to cover their tracks.

---

**7.** Which MFA factor type is considered MOST resistant to phishing attacks?

A) TOTP (time-based one-time password) via authenticator app  
B) SMS-based OTP  
C) FIDO2 hardware security key  
D) Push notification to mobile app

**Answer: C — FIDO2 hardware security key.** FIDO2 keys verify the website's origin as part of the authentication. Even if a user is phished to a fake site, the key won't authenticate because the domain doesn't match. SMS (B) is the weakest — subject to SIM swapping. TOTP (A) can be phished if the attacker proxies in real time.

---

**8.** During an investigation, the forensics team needs to create a copy of a suspect hard drive. What is the PRIMARY reason for using a write blocker during this process?

A) To speed up the acquisition process  
B) To prevent the acquisition tool from corrupting the copy  
C) To ensure no data is written to the original evidence drive  
D) To compress the forensic image

**Answer: C — To prevent any writes to the original evidence.** Any write to the original drive changes it and compromises evidence integrity. The write blocker ensures the original is not modified during acquisition.

---

---

# DOMAIN 5: SECURITY PROGRAM MANAGEMENT & OVERSIGHT
## Weight: 20% (~18 questions)

---

## 5.1 Security Governance

### Governance Documents

**Guidelines** — Recommended (not mandatory) practices for achieving security objectives. More flexible than policies.

**Policies** — Mandatory statements of management intent that define what must be done. High-level. Not prescriptive about HOW, just WHAT is required.

Key policies every organization needs:
- **AUP (Acceptable Use Policy)** — Defines appropriate and inappropriate uses of company resources
- **Information Security Policy** — Overarching security requirements
- **Business Continuity Policy** — Commitments to maintaining operations during disruption
- **Disaster Recovery Policy** — Recovery procedures after major disruptions
- **Incident Response Policy** — How incidents are handled
- **SDLC Policy** — Security requirements in software development
- **Change Management Policy** — How changes to systems are controlled

**Standards** — Mandatory, specific requirements that implement policies. Where policies say "encrypt data," standards say "use AES-256 for data at rest."

**Procedures** — Step-by-step instructions for completing a task. The HOW that implements standards and policies.

**Playbooks** — Detailed, step-by-step guides for specific incident response scenarios. "When we detect ransomware, here are the exact steps we take."

### External Governance Factors

**Regulatory** — Laws that require certain security controls or practices. Non-compliance = fines.

**Legal** — Contractual obligations, litigation requirements.

**Industry standards** — PCI DSS (payment card), HIPAA (healthcare), NERC CIP (energy grid).

**Local/Regional/National/Global** — GDPR (European Union, global reach), CCPA (California), GLBA (US financial), HIPAA (US healthcare).

### Governance Structures

**Boards** — Board of Directors; set strategic direction, high-level risk appetite.

**Committees** — Cross-functional groups (security committee, risk committee) that make tactical decisions.

**Government entities** — Regulatory bodies (SEC, FCC, state AGs) that enforce compliance.

**Centralized vs. Decentralized governance** — Centralized: one security team controls everything; consistent but may be slow. Decentralized: business units control their own security; agile but potentially inconsistent.

### Roles and Responsibilities

**Owners** — Business leaders accountable for a system or data set. They decide classification and approve access. Not the IT person.

**Controllers** — (GDPR term) Organizations that determine the purposes and means of processing personal data.

**Processors** — (GDPR term) Organizations that process data on behalf of the controller.

**Custodians/Stewards** — IT staff responsible for the technical protection of data per the owner's requirements. Day-to-day management.

---

## 5.2 Risk Management

### Risk Fundamentals

**Risk** = Likelihood × Impact

**Risk Identification** — Discovering what could go wrong. Threats × Vulnerabilities.

**Risk Assessment Types:**
- **Ad hoc** — Triggered by specific event or need
- **Recurring** — Scheduled regular assessments
- **One-time** — For a specific project or initiative
- **Continuous** — Ongoing automated risk monitoring

### Risk Analysis

**Qualitative** — Descriptive risk ratings: High, Medium, Low. Based on expert judgment. Fast but subjective.

**Quantitative** — Numerical risk calculations. More objective but requires accurate data. Key calculations the exam WILL test:

**SLE (Single Loss Expectancy)** = Asset Value × Exposure Factor
- How much money do you lose in a single incident?
- Example: Server worth $100,000, exposure factor 40% (estimated 40% of value lost in an incident) → SLE = $40,000

**ARO (Annualized Rate of Occurrence)** = How many times per year this event is expected to occur
- Example: A flood might occur 0.1 times per year (once every 10 years)

**ALE (Annualized Loss Expectancy)** = SLE × ARO
- The expected loss per year from a specific risk
- Example: SLE $40,000 × ARO 0.1 = ALE $4,000/year
- This is what you're willing to spend on controls. Don't spend $50,000/year controlling a $4,000/year risk.

**Probability/Likelihood** — How likely is the threat to occur?

**Impact** — How bad is it if it occurs?

**Exposure Factor** — The percentage of asset value lost in a single incident.

### Risk Register

A risk register is a documented list of identified risks, containing:
- **Key Risk Indicators (KRIs)** — Metrics that signal increasing risk
- **Risk Owners** — Person accountable for managing each risk
- **Risk Threshold** — The point at which a risk requires action

**Risk Tolerance** — How much risk variability an organization can absorb.

**Risk Appetite** — How much risk an organization is willing to accept in pursuit of its goals:
- **Expansionary** — High risk appetite; willing to take significant risks for growth
- **Conservative** — Low risk appetite; minimizes exposure
- **Neutral** — Balanced

### Risk Management Strategies

**Transfer** — Shift financial risk to another party. Cyber insurance transfers the financial impact of a breach to the insurer. Outsourcing to an MSP transfers some operational risk.

**Accept** — Acknowledge the risk and consciously decide not to spend resources on it. Documented with justification.
- **Exemption** — Permanent acceptance (documented reason why control doesn't apply)
- **Exception** — Temporary acceptance with a deadline and plan to remediate

**Avoid** — Eliminate the risk entirely by not doing the risky activity. Stop using a vulnerable system; don't enter a market with unacceptable regulatory risk.

**Mitigate** — Reduce the likelihood or impact through controls. The most common strategy.

### Business Impact Analysis (BIA)

Identifies critical business functions and the potential impact of disruptions.

**RTO (Recovery Time Objective)** — The maximum acceptable time to restore a system after a disruption. "We must recover this system within 4 hours." Systems with short RTOs require more redundancy.

**RPO (Recovery Point Objective)** — The maximum acceptable amount of data loss measured in time. "We can lose no more than 1 hour of transactions." Determines backup frequency.

**MTTR (Mean Time to Repair)** — Average time to repair a failed system component.

**MTBF (Mean Time Between Failures)** — Average time between failures. Higher MTBF = more reliable system.

> **RTO vs. RPO:** RTO is time-based (how long can you be down). RPO is data-based (how much data can you lose). If RTO is 1 hour, you need redundancy capable of restoring in 1 hour. If RPO is 15 minutes, backups must occur every 15 minutes.

---

## 5.3 Third-Party Risk Management

### Vendor Assessment

**Penetration Testing** — Having the vendor allow security testing of their systems to verify security claims.

**Right-to-Audit Clause** — Contractual provision allowing you to audit the vendor's security controls. Put this in every vendor contract.

**Evidence of Internal Audits** — Reviewing the vendor's own security audit results (SOC 2 reports, ISO 27001 certification).

**Independent Assessments** — Third-party security assessments of the vendor.

**Supply Chain Analysis** — Understanding who the vendor's vendors are. Your risk extends through the supply chain.

### Vendor Selection

**Due Diligence** — Thoroughly investigating a vendor before engaging them. Reviewing security practices, financial stability, references.

**Conflict of Interest** — Ensure the vendor doesn't have competing interests that could compromise your security (e.g., vendor also works with your competitors).

### Agreement Types

**SLA (Service Level Agreement)** — Defines minimum performance standards: uptime, response times, support levels. Includes penalties for failure.

**MOA (Memorandum of Agreement)** — More formal than MOU; indicates intent and describes specific roles and responsibilities between parties.

**MOU (Memorandum of Understanding)** — Non-binding document describing a general intent to work together. Often precedes a formal contract.

**MSA (Master Service Agreement)** — An overarching agreement that covers the terms for all subsequent work. Specific work is governed by Statements of Work.

**WO/SOW (Work Order/Statement of Work)** — Describes the specific work to be performed under an MSA.

**NDA (Non-Disclosure Agreement)** — Confidentiality agreement preventing disclosure of sensitive information shared during business relationships.

**BPA (Business Partners Agreement)** — Agreement between business partners describing each party's responsibilities, data sharing, security requirements.

---

## 5.4 Security Compliance

### Compliance Reporting

**Internal** — Regular reports to management and the board on compliance status.

**External** — Reports to regulators, customers, or auditors. May be mandatory (annual HIPAA assessments, PCI DSS QSA reports).

### Consequences of Non-Compliance

- **Fines** — Regulatory fines can be severe (GDPR: up to 4% of global annual revenue)
- **Sanctions** — Business restrictions, loss of ability to operate in certain markets
- **Reputational damage** — Public disclosure of non-compliance damages customer trust
- **Loss of license** — Some regulated industries (banking, healthcare) can lose their operating license
- **Contractual impacts** — Breach of contract with customers who required compliance

### Compliance Monitoring

**Due Diligence/Care** — Ongoing effort to understand and meet compliance requirements.

**Attestation and Acknowledgement** — Formal sign-off confirming compliance. Employees acknowledge they've read and understand policies.

**Automation** — Using tools to continuously monitor compliance rather than point-in-time assessments.

### Privacy

**Legal implications** — Privacy laws vary by jurisdiction:
- **Local/Regional** — CCPA (California), PIPL (China)
- **National** — HIPAA (US healthcare), GLBA (US financial)
- **Global** — GDPR (EU, but applies to any organization handling EU citizen data)

**Data Subject** — The individual whose personal data is being processed.

**Controller vs. Processor** — Controller determines purposes; processor acts on controller's behalf.

**Ownership** — Data belongs to the data subject; organizations are stewards.

**Data Inventory and Retention** — Know what data you have, where it is, how long you keep it.

**Right to Be Forgotten** — GDPR provision allowing data subjects to request deletion of their personal data.

---

## 5.5 Audits and Assessments

### Internal Audits and Assessments

**Compliance** — Verifying adherence to internal policies, standards, and procedures.

**Audit Committee** — Board-level committee overseeing the audit function. Provides independence.

**Self-assessments** — Business units assess their own compliance. Less rigorous but promotes awareness.

### External Audits and Assessments

**Regulatory** — Required by law or regulation. Example: banks must undergo FFIEC examinations.

**Examinations** — Regulators examine the organization directly.

**Independent Third-Party Audit** — External auditors (like KPMG, Deloitte) provide an objective assessment. SOC 2 reports are produced by third-party auditors.

### Penetration Testing Types

**Physical** — Testing physical security controls: can you bypass the badge reader, tailgate through a door, social engineer your way into the building?

**Offensive (Red Team)** — Simulating a real attack from an adversary perspective. Finding all possible paths to the objective.

**Defensive (Blue Team)** — The defenders who try to detect and respond to the red team.

**Integrated (Purple Team)** — Red and blue teams work together. Red team shares techniques; blue team improves detection. More collaborative and educational than pure red vs. blue.

**Known environment (White box)** — Tester has full knowledge of the environment (network diagrams, source code, credentials). Thorough but doesn't simulate a realistic external attacker.

**Partially known environment (Gray box)** — Tester has some information (like a regular employee would have). Most realistic for insider threat simulation.

**Unknown environment (Black box)** — Tester has no prior knowledge. Simulates an external attacker starting from scratch. Most realistic external attacker simulation.

**Reconnaissance:**
- **Passive** — Gathering information without directly interacting with the target (OSINT, Google, LinkedIn, Shodan). Target doesn't know they're being watched.
- **Active** — Directly interacting with the target (port scanning, sending probes). Target may detect this.

---

## 5.6 Security Awareness

### Phishing Awareness

**Phishing Campaigns** — Simulated phishing attacks sent to employees to measure susceptibility and provide immediate training to those who click.

**Recognizing a Phishing Attempt:**
- Urgency or threats ("your account will be closed in 24 hours")
- Generic greetings ("Dear Customer")
- Mismatched sender address (display name vs. actual email)
- Hover over links to see real destination
- Unexpected attachments
- Requests for credentials or sensitive information

**Responding to Reported Suspicious Messages** — Clear procedure for employees to report suspected phishing; rapid response from security team.

### Anomalous Behavior Recognition

**Risky behavior** — Employees taking actions that create risk (sharing passwords, connecting personal devices, using unsanctioned cloud services).

**Unexpected behavior** — Actions inconsistent with the user's normal patterns.

**Unintentional behavior** — Accidental policy violations (sending sensitive data to wrong recipient, losing a laptop).

### User Guidance and Training

**Policy/Handbooks** — Written documentation employees must read and acknowledge.

**Situational Awareness** — Teaching employees to recognize suspicious situations in daily work.

**Insider Threat** — Training to recognize signs of insider threat (sudden interest in systems outside job role, large data downloads, expressions of grievance).

**Password Management** — Teaching proper password hygiene and use of password managers.

**Removable Media** — Don't plug in found USB drives. Verify removable media is from trusted sources.

**Social Engineering** — Training employees to recognize manipulation tactics.

**Operational Security (OPSEC)** — Not sharing sensitive information in public forums, social media, or with unauthorized parties.

**Hybrid/Remote Work** — Security considerations for working outside the office: home network security, VPN use, physical security of devices, shoulder surfing in public.

### Reporting and Monitoring

**Initial** — Establishing the baseline of user security awareness.

**Recurring** — Regular training and awareness campaigns to keep security top-of-mind and address new threats.

---

## Domain 5 Practice Questions

**1.** A company's ERP server is valued at $500,000. Analysts estimate a ransomware attack would destroy approximately 30% of its value. Ransomware attacks are expected to occur 0.2 times per year. What is the ALE?

A) $30,000  
B) $150,000  
C) $100,000  
D) $60,000

**Answer: A — $30,000.** SLE = $500,000 × 0.30 = $150,000. ALE = SLE × ARO = $150,000 × 0.2 = $30,000.

---

**2.** An organization decides not to implement a required security control because the system is too old to be compatible. They document this decision and accept the residual risk. What is this called?

A) Risk transfer  
B) Risk exemption  
C) Risk exception  
D) Risk avoidance

**Answer: B — Risk exemption** if it's permanent (the control never applies to this system). A risk exception is temporary (with a deadline to fix). Since the system is "too old" implying it won't be updated, this is most likely an exemption. (This is a nuanced question — if the exam says "with a planned remediation date," the answer would be exception.)

---

**3.** Which agreement type defines the minimum performance levels (such as 99.9% uptime) that a service provider must meet, along with penalties for failing to meet them?

A) MOU  
B) SLA  
C) NDA  
D) BPA

**Answer: B — SLA (Service Level Agreement).** SLAs define performance standards and remedies for failing to meet them.

---

**4.** During a penetration test, the tester is given full knowledge of the network architecture, system configurations, and user credentials. What type of test is this?

A) Black box  
B) Gray box  
C) White box  
D) Red team

**Answer: C — White box (known environment).** Full knowledge of the environment. Black box = no knowledge. Gray box = partial knowledge.

---

**5.** An organization must recover critical systems within 2 hours of a disaster. Which term describes this requirement?

A) RPO  
B) RTO  
C) MTTR  
D) MTBF

**Answer: B — RTO (Recovery Time Objective).** RTO is the maximum acceptable recovery TIME. RPO is maximum acceptable data LOSS measured in time.

---

**6.** Which regulation gives EU citizens the right to request deletion of their personal data?

A) HIPAA  
B) PCI DSS  
C) GDPR  
D) GLBA

**Answer: C — GDPR.** The "right to be forgotten" or "right to erasure" is a GDPR provision.

---

**7.** A company's security team actively searches through network traffic and endpoint data for evidence of threats that have evaded existing controls. What is this activity called?

A) Vulnerability scanning  
B) Penetration testing  
C) Threat hunting  
D) Incident response

**Answer: C — Threat hunting.** Threat hunting is proactive, hypothesis-driven searching for threats that existing controls haven't detected. Vulnerability scanning is automated and looks for known vulnerabilities, not active threats.

---

---

# FULL PRACTICE EXAM — 90 QUESTIONS
## Simulate Real Exam Conditions: Set a 90-Minute Timer, No Aids

---

**1.** Which of the following BEST describes the difference between a vulnerability and a threat?

A) A vulnerability is an attack; a threat is a weakness  
B) A threat exploits a vulnerability; a vulnerability is a weakness  
C) A threat is internal; a vulnerability is external  
D) A vulnerability is malicious; a threat is accidental

**Answer: B** — A threat is anything that could exploit a weakness (vulnerability). The vulnerability is the weakness itself.

---

**2.** An organization runs critical systems that CANNOT be patched due to vendor restrictions. They implement network segmentation and enhanced monitoring. These are BEST described as:

A) Corrective controls  
B) Compensating controls  
C) Deterrent controls  
D) Directive controls

**Answer: B** — Compensating controls are alternatives used when the primary control (patching) cannot be implemented.

---

**3.** Which protocol provides the MOST secure wireless authentication by using individual session encryption and resisting offline dictionary attacks?

A) WPA2-PSK  
B) WPA3-SAE  
C) WEP  
D) WPA2-Enterprise

**Answer: B** — WPA3 with SAE (Simultaneous Authentication of Equals) is the most current and secure option, specifically addressing offline dictionary attack weaknesses in WPA2-PSK.

---

**4.** A database contains patient records. The organization replaces all Social Security Numbers with unique random tokens stored in a separate secure database. What technique is this?

A) Hashing  
B) Masking  
C) Tokenization  
D) Encryption

**Answer: C** — Tokenization replaces sensitive data with a non-sensitive surrogate (token). The mapping is stored separately. The token can be used for operations but is useless without the vault.

---

**5.** An attacker places a file in a document share and monitors who opens it to identify insider threats. The file contains no real data but triggers an alert when accessed. This is a:

A) Honeypot  
B) Honeynet  
C) Honeyfile  
D) Honeytoken

**Answer: C** — A honeyfile is specifically a fake file placed to detect unauthorized access. A honeytoken is the broader category; a honeyfile is a specific type of honeytoken.

---

**6.** Which of the following cryptographic concepts ensures that a user cannot deny performing an action?

A) Confidentiality  
B) Authentication  
C) Non-repudiation  
D) Authorization

**Answer: C** — Non-repudiation ensures actions can be proven and cannot be denied, typically through digital signatures and audit logs.

---

**7.** A company wants to prevent tailgating at a secure facility entrance. Which physical control BEST addresses this?

A) CCTV cameras  
B) Security guard  
C) Access control vestibule (mantrap)  
D) Bollards

**Answer: C** — A mantrap/access control vestibule physically prevents tailgating by requiring the first door to close before the second opens, forcing one-at-a-time entry.

---

**8.** An employee clicks a malicious link and malware is installed that periodically sends the user's keystrokes to an external server. The malware uses DNS requests to transmit the data. Which combination of attack techniques is described?

A) Keylogger + DNS hijacking  
B) Spyware + DNS tunneling  
C) Keylogger + DNS tunneling  
D) Ransomware + C2 beacon

**Answer: C** — Keylogger records keystrokes; DNS tunneling exfiltrates data via DNS queries.

---

**9.** Which hash algorithm is considered MOST secure for protecting stored passwords?

A) MD5  
B) SHA-1  
C) SHA-256 with salting  
D) SHA-256 without salting

**Answer: C** — SHA-256 with salting protects against both collision attacks and rainbow table attacks. MD5 and SHA-1 are broken. SHA-256 without salting (D) is vulnerable to rainbow tables.

---

**10.** When a user connects to an enterprise wireless network, the access point forwards credentials to a RADIUS server for verification. What IEEE standard governs this process?

A) 802.11ac  
B) 802.1X  
C) 802.1Q  
D) 802.3

**Answer: B** — 802.1X is the IEEE standard for port-based network access control, using RADIUS as the backend authentication server.

---

**11.** A CISO needs to justify a $200,000 security investment to the CFO. The relevant asset is worth $1,000,000, the exposure factor is 50%, and the ARO is 0.5. Is the investment justified?

A) No, because ALE ($250,000) exceeds the investment  
B) Yes, because ALE ($250,000) exceeds the investment cost  
C) No, because SLE ($500,000) is too high  
D) Yes, because the exposure factor requires mitigation

**Answer: B** — SLE = $1,000,000 × 0.50 = $500,000. ALE = $500,000 × 0.5 = $250,000/year. A $200,000 investment to prevent $250,000/year in expected losses is justified.

---

**12.** Which term describes software that replicates itself across a network by exploiting vulnerabilities without requiring user interaction?

A) Virus  
B) Trojan  
C) Worm  
D) Rootkit

**Answer: C** — A worm self-replicates without user interaction by exploiting network vulnerabilities. A virus needs a user to execute the infected file. A Trojan disguises itself as legitimate software.

---

**13.** During incident response, which phase comes IMMEDIATELY after containment?

A) Detection  
B) Recovery  
C) Eradication  
D) Lessons learned

**Answer: C** — The order is: Preparation → Detection → Analysis → Containment → **Eradication** → Recovery → Lessons Learned.

---

**14.** An attacker is attempting to log into user accounts using the password "Summer2023!" against 10,000 accounts. Only one attempt per account is made. What type of attack is this?

A) Brute force  
B) Dictionary attack  
C) Credential stuffing  
D) Password spraying

**Answer: D** — Password spraying: one password tried against many accounts to avoid lockout. Credential stuffing uses previously breached username/password pairs.

---

**15.** Which of the following encryption algorithms is ASYMMETRIC?

A) AES-256  
B) 3DES  
C) RSA  
D) Blowfish

**Answer: C** — RSA is asymmetric (public/private key pair). AES-256, 3DES, and Blowfish are all symmetric.

---

**16.** A user on the local network sends an ARP request. A malicious actor responds with a false ARP reply claiming their MAC address corresponds to the default gateway IP. What attack is this?

A) DNS spoofing  
B) ARP poisoning  
C) MAC flooding  
D) VLAN hopping

**Answer: B** — ARP poisoning/spoofing: sending false ARP replies to poison the ARP cache and redirect traffic through the attacker (on-path attack).

---

**17.** Which of the following is a PRIMARY benefit of SASE over traditional network security architectures?

A) Eliminates the need for firewalls  
B) Delivers security and networking as a cloud-based service at the edge  
C) Requires all traffic to route through a central data center  
D) Replaces the need for identity management

**Answer: B** — SASE converges networking (SD-WAN) and security (CASB, FWaaS, Zero Trust) delivered from the cloud, enforcing policy at the edge regardless of user location.

---

**18.** A web application fails to validate the length of a username field. An attacker enters a very long string that overwrites adjacent memory and redirects program execution. What vulnerability was exploited?

A) SQL injection  
B) XSS  
C) Buffer overflow  
D) Race condition

**Answer: C** — Buffer overflow: writing more data than a buffer can hold, overwriting adjacent memory.

---

**19.** Which document type gives an organization the legal right to audit a vendor's security controls and practices?

A) NDA  
B) SLA  
C) Right-to-audit clause  
D) MOU

**Answer: C** — A right-to-audit clause is a contractual provision specifically granting the customer the right to audit the vendor's security controls.

---

**20.** What is the PRIMARY purpose of a Certificate Revocation List (CRL)?

A) To publish new certificate requests  
B) To list certificates that have been invalidated before their expiration date  
C) To store the private keys of revoked certificates  
D) To provide certificate transparency logs

**Answer: B** — A CRL is maintained by the CA and lists certificates that have been revoked (due to compromise, change in status, etc.) before their normal expiration.

---

**21.** An organization needs to recover 24 hours of transactions that were lost in a disaster. The data loss is within acceptable limits. What metric represents this acceptable level?

A) RTO  
B) MTTR  
C) RPO  
D) MTBF

**Answer: C** — RPO (Recovery Point Objective) defines the maximum acceptable data loss measured in time. If 24 hours of data loss is acceptable, the RPO is 24 hours.

---

**22.** Which type of malware specifically targets the bootloader or Master Boot Record of a system and is particularly difficult to remove?

A) Ransomware  
B) Spyware  
C) Rootkit  
D) Worm

**Answer: C** — Rootkits can target the bootloader/MBR (bootkit) to persist before the OS loads, making them very difficult to detect and remove.

---

**23.** An analyst notices that a workstation is sending small DNS requests to the same external domain every 30 seconds, but the company has no relationship with that domain. What is the MOST likely explanation?

A) DNS cache poisoning  
B) Malware using DNS tunneling for C2 communication  
C) DNS amplification attack  
D) DNS hijacking

**Answer: B** — Regular, periodic DNS requests to an unknown external domain at machine-like intervals (every 30 seconds) is characteristic of malware beaconing via DNS tunneling.

---

**24.** A company stores EU citizen data on servers in the United States. Which concept describes the legal obligation this creates?

A) Data sovereignty  
B) Data classification  
C) Data masking  
D) Data tokenization

**Answer: A** — Data sovereignty: data is subject to the laws of the country where it is stored AND potentially the country of origin of the data subjects. Storing EU citizen data in the US triggers both GDPR and US law obligations.

---

**25.** Which access control model grants access based on the combination of user department, resource classification, and time of access?

A) MAC  
B) DAC  
C) RBAC  
D) ABAC

**Answer: D** — ABAC (Attribute-Based Access Control) makes decisions based on attributes of the user, resource, and environment, making it the most fine-grained and flexible model.

---

**26.** A Zero Trust security model has been implemented. Which component is responsible for enforcing access decisions by allowing or blocking traffic?

A) Policy Engine  
B) Policy Administrator  
C) Policy Enforcement Point  
D) Adaptive Identity

**Answer: C** — The Policy Enforcement Point (PEP) is the gate that actually allows or blocks access based on decisions from the Policy Engine (communicated by the Policy Administrator).

---

**27.** An employee reports that their computer is suddenly encrypting files and displaying a ransom note. What is the FIRST step the security team should take?

A) Pay the ransom to minimize damage  
B) Run antivirus to remove the malware  
C) Disconnect the system from the network  
D) Restore files from backup

**Answer: C** — First: CONTAIN. Disconnect from the network immediately to prevent spread to other systems and stop communication with C2. Then analyze, eradicate, then recover.

---

**28.** Which of the following BEST describes the function of a TPM chip?

A) Encrypting network traffic  
B) Managing user passwords  
C) Providing hardware-based key storage and cryptographic operations  
D) Acting as a network access controller

**Answer: C** — A TPM (Trusted Platform Module) is a hardware chip providing secure key storage, random number generation, and platform integrity measurement (attestation).

---

**29.** A new employee joins the accounting department. Following the principle of least privilege, what access should they be granted initially?

A) Full admin access to verify all permissions work  
B) Access to all accounting systems plus common shared systems  
C) Only the minimum access required for their specific job function  
D) The same access as the employee who last held that position

**Answer: C** — Least privilege: grant only what is necessary for the specific job, starting from minimum access and adding only what is needed.

---

**30.** Which of the following BEST describes the difference between IDS and IPS deployment?

A) IDS uses signatures; IPS uses anomaly detection  
B) IDS is deployed inline and can block; IPS is passive and only alerts  
C) IPS is deployed inline and can block; IDS is passive and only alerts  
D) IDS monitors network traffic; IPS monitors host activity

**Answer: C** — IPS is inline (can block). IDS is passive (alert only). Both can use signatures and/or anomaly detection.

---

**31.** After a security incident, the incident response team documents what happened, what worked well, and what needs improvement. What phase of incident response is this?

A) Eradication  
B) Recovery  
C) Lessons learned  
D) Post-containment

**Answer: C** — Lessons learned (also called Post-Incident Activity) is the final phase of the IR process.

---

**32.** A developer stores customer credit card numbers in a database but only shows the last four digits to users and staff. The full number is stored encrypted. What technique is used for the display?

A) Tokenization  
B) Masking  
C) Hashing  
D) Steganography

**Answer: B** — Masking: replacing real data with a partially redacted version for display purposes. The full number exists (encrypted) but is masked in the UI.

---

**33.** Which vulnerability type allows an attacker to navigate to unintended directories using sequences like "../../../etc/passwd"?

A) SQL injection  
B) Cross-site scripting  
C) Buffer overflow  
D) Directory traversal

**Answer: D** — Directory traversal uses path sequences to navigate outside intended directories and access sensitive files.

---

**34.** An organization processes payment card data. Which compliance framework applies?

A) HIPAA  
B) GDPR  
C) PCI DSS  
D) SOX

**Answer: C** — PCI DSS (Payment Card Industry Data Security Standard) applies to any organization that processes, stores, or transmits credit/debit card data.

---

**35.** Which of the following is TRUE about digital signatures?

A) They use the recipient's public key for signing  
B) They provide confidentiality by encrypting the message  
C) They use the sender's private key for signing  
D) They require a symmetric key for verification

**Answer: C** — Digital signatures are created using the sender's PRIVATE key. Anyone with the sender's PUBLIC key can verify the signature.

---

**36.** An organization's CISO classifies a newly discovered vulnerability as Critical (CVSS 9.8). The system in question is not internet-facing and has multiple compensating controls. What should the analyst do?

A) Immediately patch regardless of environment  
B) Consider the environmental score, which may lower effective severity  
C) Ignore the vulnerability since compensating controls exist  
D) Accept the risk permanently

**Answer: B** — CVSS has a base score, temporal score, and environmental score. The environmental score adjusts for your specific environment's exposure and compensating controls. A CVSS 9.8 base score may be lower effective severity in your environment.

---

**37.** A company's email gateway adds a cryptographic signature to all outgoing emails using the company's private key, allowing receivers to verify authenticity. What is this?

A) SPF  
B) DMARC  
C) DKIM  
D) S/MIME

**Answer: C** — DKIM (DomainKeys Identified Mail) adds a cryptographic signature to outgoing email using the domain's private key. Receivers verify with the public key from DNS.

---

**38.** Which of the following BEST describes a supply chain attack?

A) Stealing goods during physical shipment  
B) Compromising a trusted vendor or software supplier to attack their customers  
C) Using social engineering to gain physical access to a warehouse  
D) Intercepting network traffic between a client and server

**Answer: B** — Supply chain attacks compromise trusted upstream parties (vendors, suppliers, update mechanisms) to reach downstream targets.

---

**39.** An analyst discovers a server running services on ports 22, 23, 80, 443, and 3389. Which port represents the GREATEST security risk?

A) 22 (SSH)  
B) 23 (Telnet)  
C) 443 (HTTPS)  
D) 3389 (RDP)

**Answer: B** — Telnet (port 23) transmits all data in CLEAR TEXT, including passwords. In a modern environment, Telnet should never be running. SSH (22) is encrypted. RDP (3389) is a risk but is encrypted.

---

**40.** A financial institution wants to ensure a third-party cloud provider meets their security requirements. They include a clause in the contract allowing them to inspect the provider's security controls at any time. What is this clause called?

A) SLA  
B) NDA  
C) Right-to-audit clause  
D) MOU

**Answer: C** — Right-to-audit clause is the contractual provision granting the customer the right to audit vendor security.

---

**41.** What type of malware disguises itself as a legitimate, useful application to gain user trust and installation?

A) Worm  
B) Trojan  
C) Rootkit  
D) Virus

**Answer: B** — A Trojan (Trojan Horse) pretends to be legitimate software to trick users into installing it.

---

**42.** Which of the following BEST describes a honeynet?

A) A fake file used to detect unauthorized access  
B) A single decoy system designed to attract attackers  
C) A network of decoy systems designed to simulate a full network environment  
D) A fake credential used to detect credential theft

**Answer: C** — A honeynet is a network of honeypots, simulating an entire network environment.

---

**43.** A security analyst runs a vulnerability scan and receives a report indicating a critical vulnerability on a server. Upon investigation, the server doesn't actually have that service installed. What is this called?

A) False negative  
B) True negative  
C) True positive  
D) False positive

**Answer: D** — False positive: the scanner reported a vulnerability that doesn't actually exist. A false negative would be a real vulnerability the scanner missed.

---

**44.** Which of the following provides the BEST protection against a VM escape attack?

A) Running identical software on each VM  
B) Keeping the hypervisor patched and up-to-date  
C) Encrypting all VM disk images  
D) Using the same credentials for all VMs

**Answer: B** — VM escape exploits hypervisor vulnerabilities. Keeping the hypervisor patched is the primary mitigation.

---

**45.** An organization uses a SIEM to correlate security events from firewalls, IDS, and endpoint security tools. A correlation rule triggers an alert for 5 failed logins followed by a successful login from the same IP within 2 minutes. What does this indicate?

A) Normal user behavior  
B) Possible brute force followed by successful authentication  
C) DDoS attack  
D) DNS tunneling

**Answer: B** — Failed logins followed by a success suggests a brute force attack that ultimately succeeded, indicating potentially compromised credentials.

---

**46.** Which key length is the MINIMUM currently recommended for RSA asymmetric encryption?

A) 512-bit  
B) 1024-bit  
C) 2048-bit  
D) 128-bit

**Answer: C** — 2048-bit RSA is the current minimum recommended key length. 4096-bit for high security. 512 and 1024-bit are considered broken.

---

**47.** An organization implements a policy where administrative accounts can only be used between 8 AM and 6 PM, Monday through Friday. Which access control mechanism is this?

A) MAC  
B) RBAC  
C) Rule-based access control  
D) ABAC

**Answer: C** — Time-of-day restrictions enforced by the system regardless of user identity is rule-based access control.

---

**48.** Which of the following is MOST resistant to an offline dictionary attack?

A) A 4-character password  
B) A password hashed with MD5  
C) A password hashed with SHA-256  
D) A password hashed with bcrypt and a unique salt

**Answer: D** — bcrypt is a key-stretching algorithm designed specifically for password hashing. It's intentionally slow, making offline brute force/dictionary attacks computationally expensive. The unique salt prevents rainbow table attacks.

---

**49.** An employee uses a personally owned smartphone to access corporate email. What mobile deployment model is this?

A) COPE  
B) CYOD  
C) BYOD  
D) MDM

**Answer: C** — BYOD (Bring Your Own Device): employee owns the device, uses it for work.

---

**50.** A company runs multiple web servers and wants to prevent a single server failure from making the application unavailable. They also want to distribute load evenly. What should they implement?

A) Hot site  
B) RAID  
C) Load balancer  
D) VPN

**Answer: C** — A load balancer distributes traffic across multiple servers and provides failover if one server fails.

---

**51.** Which of the following represents a PASSIVE reconnaissance technique?

A) Port scanning the target  
B) Sending crafted packets to test firewall rules  
C) Searching LinkedIn for employee information  
D) Attempting to log in with default credentials

**Answer: C** — Passive reconnaissance doesn't directly interact with the target. Searching LinkedIn is passive OSINT. Port scanning, sending packets, and login attempts are all active.

---

**52.** What is the PRIMARY purpose of salting a password before hashing?

A) Increase the processing speed of hash operations  
B) Prevent two users with the same password from having the same hash  
C) Make the hash longer and harder to crack  
D) Encrypt the password before storing it

**Answer: B** — Salting adds a unique random value to each password before hashing, ensuring that identical passwords produce different hashes, defeating rainbow table attacks and making pre-computation infeasible.

---

**53.** An analyst discovers that an attacker forced a TLS 1.2 connection to downgrade to SSL 3.0 to exploit a known weakness. What type of attack is this?

A) Birthday attack  
B) Collision attack  
C) Downgrade attack  
D) Replay attack

**Answer: C** — A downgrade attack forces a communication to use an older, weaker protocol that the attacker can exploit.

---

**54.** Which of the following BEST describes the purpose of a WAF?

A) Protecting the network perimeter from all external threats  
B) Inspecting and filtering HTTP/HTTPS traffic to protect web applications  
C) Replacing the need for application-level authentication  
D) Encrypting all web traffic between clients and servers

**Answer: B** — A WAF (Web Application Firewall) specifically inspects HTTP/HTTPS traffic and protects web applications from attacks like SQLi, XSS, and CSRF.

---

**55.** During forensic investigation, the chain of custody is broken because there's no documentation of who had the evidence between 3 PM and 9 PM. What is the PRIMARY consequence?

A) The investigation must start over  
B) The evidence may be inadmissible in court  
C) The forensic images must be rehashed  
D) The evidence must be re-acquired

**Answer: B** — A broken chain of custody can render evidence inadmissible in legal proceedings because its integrity and authenticity cannot be established.

---

**56.** Which type of cloud service gives customers the MOST control over their security configurations?

A) SaaS  
B) PaaS  
C) IaaS  
D) FaaS

**Answer: C** — IaaS gives the most control — customers manage everything from the OS up, including all security configurations. SaaS provides the least customer control.

---

**57.** An organization processes data on behalf of another company. Under GDPR, what role does the organization have?

A) Data subject  
B) Data controller  
C) Data processor  
D) Data custodian

**Answer: C** — A data processor processes data on behalf of the controller. The controller determines purposes and means; the processor acts on their instructions.

---

**58.** What technique do attackers use to hide a covert communication channel within DNS queries?

A) DNS poisoning  
B) DNS hijacking  
C) DNS tunneling  
D) DNS amplification

**Answer: C** — DNS tunneling encodes data in DNS queries/responses, using DNS as a covert channel for C2 communication or data exfiltration.

---

**59.** A system administrator is hardening a new Linux server. Which of the following actions would reduce the attack surface the MOST?

A) Enabling the host-based firewall  
B) Installing antivirus software  
C) Removing unnecessary services and applications  
D) Changing the default SSH port

**Answer: C** — Removing unnecessary services and applications eliminates potential vulnerability vectors entirely. An attack surface is the sum of all possible attack vectors; removing services directly reduces it. Changing SSH port is security through obscurity.

---

**60.** An organization uses an asymmetric algorithm to securely exchange a symmetric key, which is then used to encrypt a large file. What term describes the symmetric key in this context?

A) Public key  
B) Session key  
C) Root key  
D) Ephemeral key

**Answer: B** — A session key (or bulk encryption key) is a symmetric key used for encrypting the actual data in a session. It is typically exchanged securely using asymmetric encryption.

---

**61.** An employee who left the company two weeks ago is discovered to have accessed sensitive files using their still-active account three days after termination. What process failure allowed this?

A) Inadequate monitoring  
B) Failure to de-provision the account upon termination  
C) Lack of MFA on the account  
D) Improper role assignment

**Answer: B** — De-provisioning should occur immediately upon termination. This is a fundamental IAM process failure.

---

**62.** Which of the following is a BENEFIT of using RBAC over DAC?

A) RBAC prevents all unauthorized access  
B) RBAC is enforced by the system, not users  
C) RBAC simplifies access management by assigning permissions to roles rather than individuals  
D) RBAC is more granular than DAC

**Answer: C** — RBAC simplifies management: instead of setting permissions for each individual user, you define roles and assign users to them. When someone changes jobs, change their role. DAC allows resource owners to grant access individually, which is more complex to manage at scale.

---

**63.** A threat actor registers the domain "micros0ft.com" hoping that users will mistype it. What attack technique is this?

A) Brand impersonation  
B) Watering hole  
C) Typosquatting  
D) Phishing

**Answer: C** — Typosquatting (URL hijacking): registering misspelled or look-alike domains to catch users who mistype or notice the wrong address.

---

**64.** Which of the following BEST describes the purpose of DMARC?

A) Encrypting email in transit  
B) Signing email with a cryptographic signature  
C) Authorizing which servers can send email for a domain  
D) Specifying policy for handling emails that fail SPF or DKIM checks

**Answer: D** — DMARC specifies what to do (none, quarantine, reject) when an email fails SPF and/or DKIM, and where to send reports. SPF authorizes sending servers. DKIM signs messages.

---

**65.** What is the MAIN advantage of an EDR solution over traditional antivirus?

A) EDR uses less system resources  
B) EDR doesn't require signature updates  
C) EDR detects threats based on behavior and provides investigation and response capabilities  
D) EDR is cheaper than antivirus solutions

**Answer: C** — EDR goes beyond signature matching to monitor endpoint behavior, detect anomalies, record telemetry for forensics, and support active response (isolating endpoints, killing processes).

---

**66.** A company runs a tabletop exercise where they present a hypothetical ransomware attack scenario to key stakeholders. What is the PRIMARY goal?

A) Test backup restoration capabilities  
B) Measure detection tool effectiveness  
C) Identify gaps in procedures, communication, and decision-making  
D) Train employees to recognize phishing

**Answer: C** — Tabletop exercises are discussion-based scenarios designed to identify procedural gaps, unclear roles, and communication breakdowns in incident response plans.

---

**67.** Which of the following is NOT a category of security control?

A) Technical  
B) Physical  
C) Managerial  
D) Preventive

**Answer: D** — "Preventive" is a control TYPE, not a CATEGORY. The categories are Technical, Managerial, Operational, and Physical. Types are Preventive, Deterrent, Detective, Corrective, Compensating, and Directive.

---

**68.** An attacker sends 1 million SYN packets from spoofed IP addresses to a web server, consuming all available connection slots and preventing legitimate users from connecting. What attack is this?

A) DDoS — Amplification  
B) SYN Flood (DDoS)  
C) ARP Poisoning  
D) Session hijacking

**Answer: B** — SYN Flood: sending many SYN packets from spoofed IPs to exhaust connection state tables, denying service to legitimate users.

---

**69.** An organization wants to implement the STRONGEST form of data destruction before disposing of hard drives containing classified information. What method should they use?

A) Overwriting with zeros once  
B) Formatting the drive  
C) Degaussing followed by physical destruction  
D) Full disk encryption before disposal

**Answer: C** — Degaussing destroys data magnetically; physical destruction (shredding, incineration) ensures data cannot be recovered. This combination is the strongest method. Formatting alone doesn't destroy data; overwriting once may leave recoverable traces on some media.

---

**70.** A developer finds a vulnerability in popular software and reports it to the vendor, giving them 90 days to release a patch before going public. This is an example of:

A) Bug bounty program  
B) Responsible disclosure  
C) Full disclosure  
D) Coordinated vulnerability disclosure

**Answer: D** — Coordinated vulnerability disclosure: the researcher notifies the vendor and gives them time to patch before disclosure. Responsible disclosure is similar but "coordinated disclosure" is the more precise modern term. (Both B and D could be accepted — the exam may not distinguish. The key is reporting to the vendor BEFORE going public.)

---

**71.** What is the PRIMARY security benefit of network segmentation?

A) Speeds up network traffic  
B) Eliminates the need for firewalls  
C) Limits lateral movement by containing breaches within segments  
D) Improves wireless coverage

**Answer: C** — Segmentation limits what an attacker can reach once they've compromised one system. A breach in one segment doesn't automatically provide access to other segments.

---

**72.** An organization's policy requires all system changes to be tested in a staging environment before production. A change was made directly to production without testing, causing an outage. What change management document should have prevented this?

A) NDA  
B) SLA  
C) Standard operating procedure  
D) Business continuity plan

**Answer: C** — An SOP (Standard Operating Procedure) would document the required steps including the staging environment testing requirement. Following the SOP would have prevented the skip.

---

**73.** Which mobile device security feature allows the organization to erase all data on a lost or stolen device?

A) Remote lock  
B) MDM enrollment  
C) Remote wipe  
D) Full disk encryption

**Answer: C** — Remote wipe: the capability to remotely erase all data on a mobile device. MDM is the platform; remote wipe is the specific feature.

---

**74.** A security analyst observes that a workstation regularly initiates a new HTTPS connection to the same external IP every 60 seconds. The connections transfer a small amount of data and quickly close. What is the MOST likely explanation?

A) A user streaming video  
B) Malware beaconing to a C2 server  
C) Legitimate software checking for updates  
D) A DDoS attack originating from the workstation

**Answer: B** — Regular, mechanical, low-volume connections to an external IP at precise intervals is the signature of malware beaconing to a C2 server to check for commands.

---

**75.** Which of the following frameworks provides a standardized language for describing adversary tactics, techniques, and procedures (TTPs)?

A) NIST CSF  
B) ISO 27001  
C) MITRE ATT&CK  
D) PCI DSS

**Answer: C** — MITRE ATT&CK is a knowledge base of adversary tactics and techniques used for threat intelligence, detection engineering, and security assessments.

---

**76.** An organization requires users to authenticate with a password (something you know) and a fingerprint scan (something you are). What is this called?

A) Single sign-on  
B) Federation  
C) Multi-factor authentication  
D) Identity proofing

**Answer: C** — MFA uses two or more factors from different categories. Password (something you know) + fingerprint (something you are) = MFA.

---

**77.** Which of the following BEST describes the function of a CASB?

A) An endpoint security agent that detects malware  
B) A network access controller for wired connections  
C) A security policy enforcement point between users and cloud services  
D) A certificate authority for cloud-based PKI

**Answer: C** — A CASB (Cloud Access Security Broker) sits between users and cloud services, enforcing security policies, providing visibility into cloud usage, and detecting threats.

---

**78.** An organization discovers that their wireless network can be accessed by an attacker sitting in the parking lot. Site surveys and heat maps were not conducted during deployment. What should they have done?

A) Implemented WPA3  
B) Used 802.1X authentication  
C) Adjusted AP placement and power levels based on a site survey  
D) Deployed more access points

**Answer: C** — A site survey would have identified that the wireless signal extended beyond the building perimeter. Proper AP placement and power level adjustment would have contained the signal to the intended area.

---

**79.** What type of agreement would define the roles and responsibilities between two organizations that wish to share security threat intelligence?

A) NDA  
B) SLA  
C) BPA  
D) MOU

**Answer: D** — An MOU (Memorandum of Understanding) describes a general intention to work together and defines each party's roles. For threat intelligence sharing, this is appropriate. An NDA would also be involved but covers only confidentiality.

---

**80.** An organization allows employees to work from home but requires them to use a VPN. Which type of VPN is MOST appropriate for this scenario?

A) Site-to-site VPN  
B) Remote access VPN  
C) SD-WAN  
D) Split tunneling VPN

**Answer: B** — Remote access VPN is designed for individual users connecting to the corporate network from remote locations. Site-to-site connects two entire networks.

---

**81.** A threat actor nation-state group is conducting espionage against a defense contractor. They maintain persistent access for months without detection. What category of threat actor is this?

A) Hacktivist  
B) Script kiddie  
C) Insider threat  
D) APT (Advanced Persistent Threat) / Nation-state

**Answer: D** — Nation-state actors conducting long-term, stealthy espionage are the definition of APT (Advanced Persistent Threat).

---

**82.** Which of the following BEST describes the concept of "data at rest"?

A) Data being transmitted across a network  
B) Data currently being processed by the CPU  
C) Data stored on a hard drive, database, or backup media  
D) Data captured in network packets

**Answer: C** — Data at rest is data stored on media: hard drives, SSDs, databases, tapes, USB drives. Data in transit is on the network. Data in use is in active processing/memory.

---

**83.** A hospital needs systems available 24/7. When a security patch causes a system to crash, the security team is criticized for applying it. What concept should be applied to BALANCE these competing requirements?

A) Always apply patches immediately regardless of impact  
B) Never apply patches to healthcare systems  
C) Use a change management process with testing, maintenance windows, and backout plans  
D) Only apply patches once per year

**Answer: C** — Change management balances security (patch) with availability (system stability) by requiring testing, planning maintenance windows, and having backout plans.

---

**84.** Which of the following is the PRIMARY security concern with shadow IT?

A) It increases IT costs  
B) It creates blind spots where security controls are not applied  
C) It violates software licensing agreements  
D) It requires additional user training

**Answer: B** — Shadow IT operates outside the IT department's visibility, meaning security controls (patching, monitoring, DLP, access controls) are not applied to these systems and services.

---

**85.** An attacker gains access to a web application as a regular user and then exploits a vulnerability to gain administrative privileges. What type of attack is this?

A) Horizontal privilege escalation  
B) Vertical privilege escalation  
C) Session hijacking  
D) Credential stuffing

**Answer: B** — Vertical privilege escalation: moving from a lower privilege level (regular user) to a higher one (admin). Horizontal would be accessing another user's data at the same privilege level.

---

**86.** Which backup strategy requires the LEAST storage space but takes the LONGEST time to restore?

A) Full  
B) Differential  
C) Incremental  
D) Snapshot

**Answer: C** — Incremental backups only save changes since the last backup (any type), so each incremental is small. But restoration requires the last full backup + every incremental in sequence, making it the most time-consuming restore.

---

**87.** A developer writes code that will automatically delete critical files if the developer's employee account is ever disabled. What type of malware does this represent?

A) Trojan  
B) Worm  
C) Logic bomb  
D) Ransomware

**Answer: C** — A logic bomb: malicious code with a trigger condition (account disabled). Designed to execute in the future when a specific condition is met.

---

**88.** An employee is caught downloading large amounts of sensitive data to a USB drive just before resigning. What type of threat is this?

A) External threat  
B) Nation-state threat  
C) Insider threat  
D) Supply chain threat

**Answer: C** — An insider threat: someone with legitimate internal access misusing it. This is a classic malicious insider scenario.

---

**89.** Which vulnerability arises when a program checks a file's permission at one time but reads the file at a later time, and an attacker replaces the file between these two operations?

A) Race condition (TOCTOU)  
B) Buffer overflow  
C) Memory injection  
D) SQL injection

**Answer: A** — TOCTOU (Time-of-Check to Time-of-Use) race condition: the gap between checking permissions and using the resource allows an attacker to swap the resource.

---

**90.** An organization has just experienced a data breach. Lawyers advise that litigation is likely. The security team is instructed to stop deleting any files or logs related to the incident. What is this instruction called?

A) Chain of custody  
B) E-discovery  
C) Legal hold  
D) Evidence preservation

**Answer: C** — A legal hold (also called litigation hold or preservation hold) is an instruction to preserve all potentially relevant evidence when litigation is anticipated.

---

---

# EXAM STRATEGY & FINAL TIPS

## The Day Before
- Review your weakest domain based on which practice questions you missed most
- Review the acronym list — know every acronym in the official exam objectives
- Sleep. Seriously. Tired test-takers fail.

## The Day Of
- Arrive with time to settle
- PBQs appear FIRST. If one is eating your time, FLAG IT and move on. Come back.
- Read every word of every question. CompTIA hides the answer in specific wording.
- Watch for: "BEST," "MOST," "FIRST," "PRIMARY" — eliminate wrong answers before choosing.
- If you see two answers that both look right, the one that's more complete or appropriate for the SCENARIO is usually correct.
- Trust your first instinct. Changing answers often hurts more than it helps.

## Key Mnemonics

**CIA Triad:** **C**onfidentiality, **I**ntegrity, **A**vailability — every security decision maps to one of these.

**IR Order (PICERL):** **P**reparation → **I**dentify/Detect → **C**ontain → **E**radicate → **R**ecover → **L**essons Learned  
Mnemonic: "**P**eople **I**n **C**yber **E**vents **R**equire **L**eadership"

**SPF / DKIM / DMARC:**  
- SPF = who can **S**end  
- DKIM = **D**idn't tamper (**K**ey-signed)  
- DMARC = what to **D**o when the others fail  

**ALE Formula:** ALE = SLE × ARO = (Asset Value × Exposure Factor) × ARO

**MFA Factors:**  
- Know = password, PIN  
- Have = token, phone, smart card  
- Are = biometrics  
- Where = geolocation  

**Risk Strategies (TAMA):**  
**T**ransfer · **A**ccept · **M**itigate · **A**void

**Backup Restore Speed (slowest to fastest restore):**  
Incremental → Differential → Full

**Firewall Types (least to most capable):**  
Packet Filter → Stateful → UTM → NGFW → WAF

---

## Acronyms You Must Know Cold

| Acronym | Full Name |
|---|---|
| AAA | Authentication, Authorization, Accounting |
| ACL | Access Control List |
| AES | Advanced Encryption Standard |
| ALE | Annualized Loss Expectancy |
| ARO | Annualized Rate of Occurrence |
| AUP | Acceptable Use Policy |
| BIA | Business Impact Analysis |
| BPA | Business Partners Agreement |
| BYOD | Bring Your Own Device |
| CA | Certificate Authority |
| CASB | Cloud Access Security Broker |
| CIA | Confidentiality, Integrity, Availability |
| COPE | Corporate-Owned, Personally Enabled |
| CRL | Certificate Revocation List |
| CSR | Certificate Signing Request |
| CVE | Common Vulnerabilities and Exposures |
| CVSS | Common Vulnerability Scoring System |
| CYOD | Choose Your Own Device |
| DAC | Discretionary Access Control |
| DDoS | Distributed Denial of Service |
| DHE | Diffie-Hellman Ephemeral |
| DKIM | DomainKeys Identified Mail |
| DLP | Data Loss Prevention |
| DMARC | Domain-based Message Authentication Reporting and Conformance |
| EAP | Extensible Authentication Protocol |
| EDR | Endpoint Detection and Response |
| FDE | Full Disk Encryption |
| FIM | File Integrity Monitoring |
| HSM | Hardware Security Module |
| IaC | Infrastructure as Code |
| ICS | Industrial Control Systems |
| IDS | Intrusion Detection System |
| IPS | Intrusion Prevention System |
| IoT | Internet of Things |
| JIT | Just-in-Time |
| MAC | Mandatory Access Control |
| MAC | Media Access Control (different context) |
| MDM | Mobile Device Management |
| MOA | Memorandum of Agreement |
| MOU | Memorandum of Understanding |
| MSA | Master Service Agreement |
| MTBF | Mean Time Between Failures |
| MTTR | Mean Time to Repair |
| MFA | Multi-Factor Authentication |
| NAC | Network Access Control |
| NDA | Non-Disclosure Agreement |
| NGFW | Next-Generation Firewall |
| OCSP | Online Certificate Status Protocol |
| PAM | Privileged Access Management |
| PKI | Public Key Infrastructure |
| RBAC | Role-Based Access Control |
| RPO | Recovery Point Objective |
| RTOS | Real-Time Operating System |
| RTO | Recovery Time Objective |
| SASE | Secure Access Service Edge |
| SCADA | Supervisory Control and Data Acquisition |
| SD-WAN | Software-Defined Wide Area Network |
| SDN | Software-Defined Networking |
| SIEM | Security Information and Event Management |
| SLA | Service Level Agreement |
| SLE | Single Loss Expectancy |
| SOW | Statement of Work |
| SPF | Sender Policy Framework |
| SSH | Secure Shell |
| SSO | Single Sign-On |
| TLS | Transport Layer Security |
| TPM | Trusted Platform Module |
| UPS | Uninterruptible Power Supply |
| UTM | Unified Threat Management |
| VPN | Virtual Private Network |
| WAF | Web Application Firewall |
| XDR | Extended Detection and Response |

---

*This guide covers 100% of the SY0-701 exam objectives as published by CompTIA. Good luck.*
