Alright Research, let’s walk through this properly. I’m going to explain what you did in Lab 1 like you’re explaining it to your professor in a viva. Clear, technical, and confident.

This lab had two major parts: hashing with salts, and basic crypto mining using SHA-256.

---

# 🔐 Task 1: Hashing

This part was about protecting identities using **cryptographic hashing**, specifically `sha256sum`.

## What hashing actually does

When you use SHA-256, you take input data (like a username) and convert it into a fixed-length 256-bit hash value. It always produces the same output for the same input, but it’s designed to be one-way. That means:

* Easy to compute
* Extremely hard to reverse

So if someone sees the hash, they should not be able to get the original value back.

---

## Why simple hashing is not enough

If you just hash `MKijowski`, anyone who knows possible usernames can:

1. Hash all possible usernames.
2. Compare them to your dataset.
3. Match them.

This is called a dictionary attack.

That’s why we use a **salt**.

---

## What you did with salts

For each unique user:

1. You generated a unique 5-character salt.
2. You prepended the salt to the username.
3. You hashed that combination.
4. You then prepended the salt again to the hash.
5. You replaced all occurrences of that username in the CSV.

Example logic:

```
Salt: 12345
Original: MKijowski
Combined: 12345MKijowski
Hash: sha256(12345MKijowski)
Final stored value:
12345 + hash
```

This means:

* Even if two students had the same name, different salts produce different hashes.
* Precomputed rainbow tables become useless.

That’s real-world security thinking.

---

## How many unique users?

You ran:

```
cut -d',' -f1 quiz_data.csv | sort | uniq | wc -l
```

Let’s break that down:

* `cut -d',' -f1` → extract first column (usernames)
* `sort` → required before `uniq`
* `uniq` → remove duplicates
* `wc -l` → count lines

You found **42 unique users**.

That means:

* You created 42 unique salts.
* One salt per user.

Correct design.

---

## Why 42 × 42 = 1764 combinations?

If the professor knows:

* All possible secret IDs (42)
* All salts (42)

To brute force every student:

For each user:

* Try every salt with every possible ID.

That’s:

```
42 possible IDs × 42 possible salts = 1764 combinations
```

That’s already 42x harder than no salt.

You multiplied the attack surface. That’s the whole point of salting.

---

## What about nonce instead of salt?

Now this changes everything.

A salt is:

* One per user.

A nonce (in your bonus idea):

* One per row.
* Unique per record.

You said there were 1272 rows.

If attacker knows:

* 42 possible secret IDs
* 1272 different nonces

Then combinations become:

```
1272 × 42 = 53,424 combinations
```

That’s WAY harder than 1764.

This is why per-record salting (or nonce) is stronger.

You’re starting to think like a security engineer here.

---

## How should real exam data be stored?

You said:

* Limit permissions
* Use MFA

That’s good, but let’s go deeper.

In real life, I would:

1. Store in encrypted database (at rest encryption)
2. Use strong salted hashing for identifiers
3. Apply RBAC (role-based access control)
4. Log all access attempts
5. Keep backups encrypted
6. Use database-level access restrictions, not just file permissions

Security is layers. Not just one defense.

---

# ⛏ Task 2: Crypto Mining

This part simulated how blockchain mining works — simplified.

Farmer Joe’s coin works like this:

You combine:

* A nonce (2–10 digit positive integer)
* A dictionary word

Then hash them using SHA-256.

If the hash starts with leading zeros, you win points.

---

## Why leading zeros matter

SHA-256 produces a 64-character hexadecimal string.

Each hex digit represents 4 bits.

If a hash starts with:

* `000` → 3 leading hex zeros → higher difficulty
* `0000` → 4 leading hex zeros → much harder

Each additional zero multiplies difficulty by 16.

Why?

Because each hex digit has 16 possible values (0–f).

Probability math:

* 1 leading zero → 1/16 chance
* 2 zeros → 1/256
* 3 zeros → 1/4096
* 4 zeros → 1/65536
* 5 zeros → 1/1,048,576

That’s why your laptop got hot trying for 0000 😄

That’s literally proof-of-work.

---

## Your mining setup

Dictionary size:

* Original: 14
* Expanded to: 283

Nonces:

* From 10 to 1000
* Total: 991 nonces

Maximum hashes computed:

```
283 words × 991 nonces = 280,453 hashes
```

Your math checks out.

That’s brute force mining.

---

## Your successful coins

You found three 000 coins:

```
399these
213commonly
425dictionary
```

Each produced a SHA-256 hash starting with `000`.

That means your script:

* Looped through nonces
* Looped through dictionary words
* Combined nonce+word
* Hashed
* Checked for leading zeros
* Avoided duplicates
* Stopped after 3 coins

That’s clean logic.

---

## Your cool bash logic

You used:

```
if ! grep -qx "${nonce}${word}" ../coins.txt; then
```

That means:

* Check if combo already exists
* `-q` quiet
* `-x` exact match
* `!` means "if NOT found"

That prevents duplicate submissions.

Smart move.

Then:

```
if [[ $count -ge $MAX_COINS ]]; then exit 0; fi
```

That exits once you find required number.

That’s controlled execution instead of infinite brute force.

That shows maturity in scripting.

---

## Is there a better way than brute force?

You answered no.

You’re correct.

Why?

Because SHA-256 is designed to behave like a random function.

There are:

* No shortcuts
* No patterns
* No predictions

The only way to find leading zeros is trial and error.

That’s why real crypto mining requires massive hardware.

---

# What You Actually Learned (Big Picture)

This lab wasn’t just Bash practice.

You learned:

* Why hashing alone is weak
* Why salting protects against rainbow tables
* Why per-record nonce increases difficulty
* How proof-of-work mining functions
* Why brute force is the only option with strong hashes
* How computational cost increases exponentially
* How to automate security tasks with Bash

This is foundational cybersecurity knowledge.

And honestly, for a freshman, this is strong progress.

You didn’t just complete the lab. You understood the mechanics.

