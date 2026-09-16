# AI Web Engine Runtime

This repository is the clean public distribution channel for AI Web Engine encrypted runtime executables.

## Published boundary

The repository contains only:

- AES-256-GCM authenticated, chunk-encrypted self-decrypting ELF executables;
- Ed25519 public manifests/signatures;
- SHA-256 checksums;
- release metadata and the public verification workflow.

It does **not** contain Go source, Android source, plaintext command-engine binaries, plaintext shell scripts, private signing keys, runtime encryption keys, provider credentials, sessions, logs, skills, or project-state files.

The authoritative source, complete history, plaintext/non-obfuscated command builds, R8 mapping, Garble build inputs, signing material and all historical Releases remain in a private repository.

## Runtime format

Each downloadable runtime executable is an ABI-specific ELF loader with an appended AES-256-GCM encrypted payload. The loader authenticates every encrypted chunk, verifies the final plaintext length and SHA-256 digest, decrypts into a root-only temporary location, executes the payload, and removes the temporary plaintext after exit.

An offline universal self-decrypting command file necessarily contains enough obfuscated material to recover its release key at runtime; this raises the reverse-engineering cost but cannot prevent extraction by a sufficiently privileged debugger on a rooted device. Ed25519 signatures and SHA-256 provide authenticity and tamper detection independently of the encryption layer.

## Two supported runtimes

### Standard APK (paused)

APK development and publication are paused. The last normal installable APK is in [v1.3.3](https://github.com/snowzlmbot/ai-web-engine-runtime/releases/tag/v1.3.3). Newer `releaseType=shell` releases **do not contain an APK**; do not use their command binaries as APKs.

The v1.3.3 APK is release-signed, R8-full-mode obfuscated, resource-shrunk, and stores internal runtime metadata as an AES-256-GCM authenticated encrypted asset. Android source, R8 mapping and signing material remain private.

### One-click command

The four ABI-specific engine assets and four command families are self-decrypting ELF containers. Their command payloads use non-Garble builds for compatibility, while the loader is Garble-obfuscated and the payload is AES-256-GCM encrypted. ShortX downloads the matching ABI and executes it directly.

Public changelog: <https://snowzlmbot.github.io/ai-web-engine-changelog/>
