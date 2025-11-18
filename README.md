#  X401 Protocol

# Token-gated authentication for Solana wallets using HTTP 401


  ```Built for Solana```


---

## 🌟What is X401?



X401 is an open-source protocol that leverages **HTTP 401 Unauthorized** to enable token-gated access and ephemeral data generation for Solana wallets.

It provides a clear, standardized approach to enforcing token-based and signature-based authentication while maintaining full compatibility with standard HTTP 401 semantics.

**Currently supports:**
* **One time Telegram invite links** as ephemeral data — generated on-demand when users authenticate with their wallet and hold the required token
* **One time Discod invite links** as ephemeral data — generated on-demand when users authenticate with their wallet and hold the required token
* **Custom  exclusive content** accessible only when users authenticate with their wallet and hold the required token 

The protocol is architected to support any type of ephemeral data generation in the future.

---

## 💸 The Payless Alternative to x402

While **x402** uses the `HTTP 402 Payment Required` status code to enable **micropayments** for on-demand resource access, **X401** is its **payless counterpart**

* **X401 (401 Unauthorized):** Access is granted based on **authorization** (wallet signature) and **asset ownership** (holding a specific token). **No on-chain transaction or gas fee is required** to prove access rights, making it a powerful **"payless gateway"** for exclusive content.

* **x402 (402 Payment Required):** Access is granted only after a **micropayment** is successfully submitted and verified on-chain.

**X401 enabling payless, ownership-based access for on-the-fly generation of access links.**

---

## ✨ Key Features

* 🎯 **Standards-Compliant** — Built on HTTP 401 for seamless integration with existing web infrastructure
* 🔗 **Solana-Native** — Designed specifically for Solana wallet authentication and asset verification
* 🔒 **Token-Gated** — Control access based on token ownership (SPL tokens) and wallet signatures
* 🚀 **Simple** — Easy to implement, understand, and integrate into existing backends
* 🌐 **Open Source** — Community-driven and transparent, licensed under the MIT License

---

## 🚦 Use Cases

* **Token-gated on-the-fly generation of ephemeral exclusive content** — private Telegram/Discord invite links, custom content  and more

---

## 🛠️ How It Works

The protocol follows a simple challenge-response mechanism:

1. **Challenge** — Server responds with `HTTP 401 Unauthorized` containing authentication requirements (e.g., "Must hold 1 $MYTOKEN")

2. **Verification** — Client signs a message to prove wallet ownership and submits proof of token holding

3. **Access** — Server validates credentials, confirms token ownership, and upon success, generates the requested ephemeral data (currently Telegram invite links)

---

## 🤝 Contributing

We welcome contributions from the community! Whether you're fixing bugs, improving documentation, or proposing new features — every contribution matters.

* 🐛 **Report issues**
* 💡 **Suggest features**
* 🔧 **Submit pull requests**
* 📖 **Improve documentation**



## 📄License

**MIT License** — Free to use and modify.
