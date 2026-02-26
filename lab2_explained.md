Alright Research, let’s walk through exactly what you did in this lab, step by step, in a clean and detailed way. I’ll break it down technically so you fully understand it and can explain it confidently to your professor.

---

# 🔐 Overall Goal of the Lab

You were given two leaked password hash files:

* `sha512.hashes`
* `yescrypt.hashes`

Each line in those files was taken from `/etc/shadow`, meaning:

* The password is **not stored in plain text**
* It is **salted**
* It is **hashed**

Your job was to recover as many original passwords as possible using:

* `hashcat`
* `john`
* Dictionary files like `500_passwords.txt`
* Optional advanced methods like rules or rockyou

---

# 🧠 Task 1 — Simple Dictionary Attack

## 1️⃣ What You Actually Did

You performed a **basic dictionary attack** against:

* 112 SHA-512 hashes
* 205 yescrypt hashes
* Using a 500-word dictionary

### What that means technically:

For every hash:

1. The tool reads the salt from the hash string.
2. It takes one word from the dictionary.
3. It combines the word + salt.
4. It hashes it using the same algorithm (SHA-512 or yescrypt).
5. It compares the result to the stored hash.
6. If they match → password cracked.

It repeats that process:

* For every word
* For every hash

That’s brute-forcing using a limited dictionary.

---

## 2️⃣ What is a Basic Dictionary Attack (Deep Explanation)

You correctly explained it, but let’s sharpen it technically.

A basic dictionary attack:

* Uses a predefined list of common passwords
* Tests each word exactly as written
* Does NOT modify them
* Does NOT try variations
* Does NOT try brute force combinations

### Why salting matters

Each password hash includes a salt:

Example:

```
$6$d1gWjURFVstVjUpd$6eBD1QlS7HMwmimKpVeFWUCB9iE7LHa...
```

* `$6$` → SHA-512
* `d1gWjURFVstVjUpd` → salt
* The rest → hash

The salt prevents:

* Precomputed rainbow table attacks
* Reusing the same cracked hash for multiple users

So the tool must compute hashes fresh every time.

That’s why cracking takes time.

---

## 3️⃣ Results You Got

### SHA-512 Results

* Total hashes: 112
* Cracked: 24
* Remaining: 88

Common cracked passwords:

* 12345
* password
* pass
* 123456
* letmein
* apple
* cheese
* sailorm00n

What this tells you:

Users pick extremely predictable passwords.

Even with a tiny 500-word list, you cracked 24 accounts.

That’s huge from a security perspective.

---

### Yescrypt Results

* Total hashes: 205
* Cracked: 33

Yescrypt is much slower and stronger than SHA-512.

So cracking 33 with only 500 words shows many users still used weak passwords.

---

## 4️⃣ How Many Hash Computations Happened?

You calculated this correctly.

SHA-512:

```
112 hashes × 500 words = 56,000 attempts
```

Yescrypt:

```
205 hashes × 500 words = 102,500 attempts
```

Total:

```
158,500 hash computations
```

That means your system performed 158,500 full cryptographic hash operations.

And yescrypt hashes are computationally expensive by design.

So even though you only cracked some passwords, the system still tested all combinations.

That’s important.

---

# 🔥 Task 2 — Rule-Based Attack

You chose:

> Rule-based attack using John and the same 500-word list

Good choice. That shows deeper understanding.

---

## 1️⃣ What a Rule-Based Attack Actually Does

In Task 1:

* Only tested exact words from dictionary

In Task 2:

* You enabled `--rules`
* John modified each base word automatically

Examples of rule transformations:

* password → Password
* password → password1
* batman → batman3
* orange → oranges
* hello → Hello1

So instead of 500 words, John generated thousands of variations from each base word.

This dramatically increases candidate space.

---

## 2️⃣ Command You Used

```
john --wordlist=dictionaries/500_passwords.txt --rules data/sha512.hashes
```

What this did:

* Loaded 500 base words
* Applied built-in rule engine
* Generated modified versions
* Hashed each candidate
* Compared to SHA-512 hashes

---

## 3️⃣ What Happened During Execution

John reported:

* ~1300 candidates per second
* Ran for 20 minutes (1200 seconds)

Estimated computations:

```
1300 × 1200 = 1,560,000 candidates tested
```

So you jumped from:

158,500 attempts (Task 1)

To:

~1.5 million attempts (Task 2)

That’s nearly 10x more testing.

That’s real scaling.

---

## 4️⃣ New Passwords Found

You cracked 4 new ones:

* Password
* Password1
* batman3
* oranges

Why weren’t they found before?

Because in Task 1:

* Only exact lowercase dictionary words were tested.

If dictionary had:

```
password
batman
orange
```

It would NOT try:

* Password
* Password1
* batman3
* oranges

Rules created those automatically.

That’s the power difference.

---

## 5️⃣ Why You Stopped at 23%

John showed:

* Only 23% of rule space completed
* You aborted at 20 minutes

Meaning:

The total possible modified candidates was far larger than what you tested.

If you let it finish:

* It might have cracked more
* But time cost increases exponentially

---

# 📊 Overall Password Analysis

From 112 SHA-512 hashes:

* Cracked 28 total (after rules)
* 84 still uncracked

Trends you noticed:

Most cracked passwords were:

* Numeric sequences
* Common words
* Word + number pattern
* Capitalized word

This confirms:

Users use predictable patterns.

Uncracked passwords likely:

* Longer
* Not in dictionary base words
* Random combinations
* More complex

To crack remaining ones, you would need:

* Larger wordlist (millions of entries)
* Rockyou.txt
* Custom rules
* Hybrid attacks
* GPU acceleration
* Much more time

---

# 🖥 Why Hardware Matters

You mentioned your computer getting hot.

Important point:

Hash cracking is CPU/GPU intensive because:

* Each guess requires full cryptographic computation
* Yescrypt is intentionally slow
* Designed to resist GPU acceleration

High-end GPUs can test:

* Millions or billions of SHA-512 per second
* But yescrypt resists that advantage

That’s why your i7 struggled with rockyou estimate of 17 days.

That’s realistic.

---

# 🎯 What This Lab Really Taught You

This lab wasn’t about cracking passwords for fun.

It demonstrated:

1. Weak passwords are extremely common.
2. Salting prevents rainbow tables.
3. Hashing alone doesn’t protect weak passwords.
4. Dictionary attacks scale quickly.
5. Rule-based attacks massively expand attack surface.
6. Hardware power changes attack feasibility.
7. Yescrypt is stronger than SHA-512 for password storage.

---

# 🚀 If You Had Unlimited Resources

To crack everything, you’d need:

* Rockyou (14+ million passwords)
* Advanced rule sets
* Hybrid attacks
* Mask attacks
* Distributed cracking cluster
* Days or weeks of runtime

And even then:
Some passwords may still remain uncracked.

Because truly random 12+ character passwords are practically infeasible to brute force.

---

# 🧠 From a Cybersecurity Perspective

As a future system security analyst, this lab teaches you:

* Why enforcing password complexity policies matters
* Why slow hash algorithms are important
* Why password reuse is dangerous
* Why multi-factor authentication is necessary
* Why salted hashing is essential

This wasn’t just a lab.

It was an offensive security demonstration of how real breaches happen.

---

If you want, I can now:

* Turn this into a clean polished submission format
* Or turn it into an oral-defense explanation so you can explain it confidently in class
* Or help you understand hashcat internals deeper

You did solid work here. This is real cybersecurity learning.
