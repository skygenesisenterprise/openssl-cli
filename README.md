# 🚀 Enterprise OpenSSL CA CLI

**Repository:** `openssl-cli`  
**Maintainer:** Sky Genesis Enterprise  
**Project:** Enterprise OpenSSL Certification Authority

---

## 🌐 Overview

The **Enterprise OpenSSL Certification Authority CLI** (`openssl-cli`) is the official command-line interface designed to interact with the Enterprise OpenSSL Certification Authority server.

This CLI tool provides developers, system administrators, and automation pipelines with a secure, reliable, and user-friendly interface to generate keys, request certificates, renew, revoke, and manage certificate lifecycles in a consistent manner across all Sky Genesis Enterprise deployments.

> ⚠️ This project is an internal and open-source initiative by Sky Genesis Enterprise and is not affiliated with the official OpenSSL Project.

---

## 🛠️ Features

- 🔐 Generate private keys and Certificate Signing Requests (CSRs)  
- 🏷️ Request, renew, and revoke X.509 certificates from the Enterprise CA  
- 📜 Manage certificate profiles and policies locally  
- 🔄 Support for automated certificate renewal  
- 🌍 Interact securely with the CA server via REST APIs  
- 🧪 Output formats: PEM, DER, JSON  
- ⚙️ Fully scriptable CLI commands for DevOps workflows  
- 🔒 Built-in verification of trusted installation source  
- 📦 Cross-platform support: Linux, macOS, Windows (planned)  

---

## ⚡ Installation

The recommended installation method is via the official Sky Genesis Enterprise source:

```bash
wget -qO- https://ssl.skygenesisenterprise.com/install-cli.sh | bash
````

This script downloads, verifies, and installs the `openssl-cli` binary with secure defaults.

---

## 🚀 Quickstart

Initialize a new key and generate a CSR:

```bash
openssl gen-key --name "my-service-key" --out ./keys/
openssl gen-csr --key ./keys/my-service-key.pem --cn "service.example.com" --out ./csr/service.csr
```

Request a certificate from the Enterprise CA:

```bash
openssl request-cert --csr ./csr/service.csr --profile tls-server --out ./certs/service.crt
```

Renew an existing certificate:

```bash
openssl renew-cert --cert ./certs/service.crt --out ./certs/service-renewed.crt
```

Revoke a certificate by serial number:

```bash
openssl revoke-cert --serial 0A1B2C3D --reason "key-compromise"
```

---

## 🧑‍💻 Development

This project is implemented in Go and is designed to be modular and extensible.

Contributions and feedback are welcome! Please follow the contributing guidelines in the `CONTRIBUTING.md` file.

---

## 🔐 Security

* All CLI releases are signed and checksummed
* Enforces secure transport (TLS) when communicating with CA servers
* Validates server certificates and fingerprints
* Supports integration with Hardware Security Modules (HSM) via PKCS#11 (planned)

---

## 📫 Contact & Support

For questions, support, or commercial inquiries:

* Website: [https://skygenesisenterprise.com](https://skygenesisenterprise.com)
* Email: [security@skygenesisenterprise.com](mailto:security@skygenesisenterprise.com)
* GitHub: [Enterprise Github Organisation](https://github.com/skygenesisenterprise)

---

## 📝 License

This project is licensed under the **MIT License**.

© Sky Genesis Enterprise. All rights reserved.