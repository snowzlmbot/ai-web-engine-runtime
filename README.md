# AI Web Engine Runtime

This repository is the clean public distribution channel for AI Web Engine encrypted runtime executables.

## Published boundary

The repository contains only:

- AES-256-GCM authenticated, chunk-encrypted self-decrypting ELF executables;
- Ed25519 public manifests/signatures;
- SHA-256 checksums;
- release metadata and the public verification workflow.

It does **not** contain Go source, Android source, plaintext engine binaries, plaintext shell scripts, raw APK files, private signing keys, runtime encryption keys, provider credentials, sessions, logs, skills, or project-state files.

The authoritative source, complete history, plaintext/non-obfuscated builds, R8/Garble build inputs, raw signed APK and all historical Releases remain in a private repository.

## Runtime format

Each downloadable runtime executable is an ABI-specific ELF loader with an appended AES-256-GCM encrypted payload. The loader authenticates every encrypted chunk, verifies the final plaintext length and SHA-256 digest, decrypts into a root-only temporary location, executes the payload, and removes the temporary plaintext after exit.

An offline universal self-decrypting file necessarily contains enough obfuscated material to recover its release key at runtime; this raises the reverse-engineering cost but cannot prevent extraction by a sufficiently privileged debugger on a rooted device. Ed25519 signatures and SHA-256 provide authenticity and tamper detection independently of the encryption layer.

Public changelog: <https://snowzlmbot.github.io/ai-web-engine-changelog/>
