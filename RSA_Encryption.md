# 🔐 RSA Encryption — Simple Breakdown

RSA is an asymmetric crypto system — meaning it uses **two different keys**:

* **Public key:** used to encrypt
* **Private key:** used to decrypt

If you encrypt something with the public key, only the private key can unlock it.

---

## 🧠 How It Works

### **1️⃣Key Generation**

RSA starts by generating two *big* prime numbers:

```
p and q
```

Multiply them:

```
n = p × q   ← modulus
```

Then calculate something called φ(n):

```
φ(n) = (p − 1)(q − 1)
```

Pick a number `e` that shares no common factors with φ(n):

```
public exponent e (almost always 65537)
```

Then compute the modular inverse of `e` mod φ(n):

```
d = e⁻¹ mod φ(n)
```

Now you have:

* **Public key:** `(n, e)`
* **Private key:** `(n, d)`

That’s it — keys generated.

---

### **2️⃣ Encryption**

To encrypt a message `m` using the public key:

```
c = m^e mod n
```

The result `c` is ciphertext.

---

### **3️⃣ Decryption**

To decrypt ciphertext `c` using the private key:

```
m = c^d mod n
```

You get your original message back.

---

 If A wants to send a msg m to B:    
 * A -> encrypt m with B' public key, get c
 * B -> decrypt c with B' private key, get back m

## 🛡 Why RSA is Secure

The security comes from the fact that given **only** `n` (which is hundreds or thousands of bits), it is insanely hard to calculate the original `p` and `q`. As long as p & q are not close to each other.      
There's **only** one pair `(p,q)` that gives `n`

---
## Credits:
ChatGPT 😘
