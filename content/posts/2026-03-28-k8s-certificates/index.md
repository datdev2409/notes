---
title: "Generate Certificates for K8s Components (CA)"
date: 2026-03-28
tags: ["kubernetes", "security", "certificates", "openssl"]
categories: ["Kubernetes Security"]
description: "Notes on how to manually generate Certificate Authority (CA) keys and self-signed certificates for Kubernetes components using OpenSSL."
draft: true
---

# Generate certificate for K8S components

## Certificate Authority (CA)

> [!IMPORTANT]
> All certificates in a Kubernetes cluster must be signed using the Certificate Authority (CA).

The CA private key is stored securely in the cluster setup and is used to sign other certificates. The CA public key is distributed to verify those signatures across components.

*(Flow: `key` → `csr` → `crt` → `p12`)*

```bash
# 1. Generate the private key (ca.key)
openssl genrsa -out ca.key 2048

# 2. Generate the Certificate Signing Request (CSR) from ca.key
openssl req -new -key ca.key -out ca.csr -subject '/CN=KUBERNETES-CA'

# 3. Generate and self-sign the cert (ca.crt)
openssl x509 -req -in ca.csr -key ca.key -out ca.crt
```
