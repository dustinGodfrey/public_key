# 🔐 Dustin's Public Certificate

This repository contains my public certificate (`dustin_pubkey.crt`) that you can use to:

- 🔒 Encrypt secure messages to me
- ✅ Verify digital signatures I've made
- 🧾 Validate that this certificate is trusted (via my Root CA)

---

## 📬 Encrypt a Message to Me

To encrypt a plaintext message (`message.txt`) using my public cert:

```bash
openssl pkeyutl -encrypt -inkey dustin_pubkey.crt -certin -in message.txt -out encrypted_for_dustin.bin
```

After running the command, send me the file `encrypted_for_dustin.bin` through any secure channel (email, upload, etc.).  
I will use my private key to decrypt it.

If you want to verify that this certificate is legitimate, you can do so with my Root CA certificate (`ca.crt`) included in this repo:

```bash
openssl verify -CAfile ca.crt dustin_pubkey.crt
```
