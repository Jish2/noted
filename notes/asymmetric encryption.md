---
updated: 2025-12-16T15:55
created: 2025-09-03T14:08
---
#networking #system-design
uses public key to encrypt and private to decrypt.
anyone can encrypt but only someone with the private key can decrypt

basically, anyone can send me a message securely

very expensive

used in [[https]] handshake (not transport though, switches to [[symmetric encryption]])

### walkthrough

### Step 1: Key generation (done by Bob)

Bob secretly chooses two primes:

- $p = 5$
- $q = 11$

Compute:

$$
n = pq = 55
$$

Compute Euler’s totient:

$$
\varphi(n) = (p-1)(q-1) = 4 \cdot 10 = 40
$$

Choose a public exponent:

$$
e = 3
$$

Find a private exponent $d$ such that:

$$
ed \equiv 1 \pmod{40}
$$

One solution is:

$$
d = 27 \quad \text{since } 3 \cdot 27 = 81 \equiv 1 \pmod{40}
$$

**Keys:**

- Public key: $(e, n) = (3, 55)$
- Private key: $(d, n) = (27, 55)$

Bob publishes $(3, 55)$ and keeps $27$ secret.

---

### Step 2: Encryption (done by Alice)

Alice wants to send the message:

$$
m = 7
$$

She encrypts using Bob’s **public key**:

$$
c = m^e \bmod n = 7^3 \bmod 55
$$

Compute:

$$
7^3 = 343,\quad 343 \bmod 55 = 13
$$

So the ciphertext is:

$$
c = 13
$$

Alice sends **13** to Bob.

---

### Step 3: Decryption (done by Bob)

Bob decrypts using his **private key**:

$$
m = c^d \bmod n = 13^{27} \bmod 55
$$

Evaluating this (via modular exponentiation) yields:

$$
m = 7
$$

The original message is recovered.

---

## Why This Works (Short Theory Note)

The exponents $e$ and $d$ are chosen so that:

$$
ed \equiv 1 \pmod{\varphi(n)}
$$

This means there exists an integer $k$ such that:

$$
ed = 1 + k\varphi(n)
$$

Because of this structure, exponentiating by $e$ and then by $d$ returns the original message:

$$
(m^e)^d \equiv m \pmod n
$$

The critical point is:

- **Computing $d$ requires knowing $\varphi(n)$**
- **Computing $\varphi(n)$ requires factoring $n$ into $p$ and $q$**
- Factoring large $n$ is computationally infeasible

So:

- Anyone can encrypt using $(e, n)$
- Only the holder of $d$ can decrypt

This is the core asymmetry behind RSA.
