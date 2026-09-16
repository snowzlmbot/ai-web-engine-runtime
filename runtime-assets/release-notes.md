# AI Web Engine v1.3.2

Public distribution contains two normal user-facing runtimes:

1. ai-web-engine.apk is a standard directly installable Android APK, signed, R8-obfuscated, resource-shrunk, and built with encrypted internal runtime metadata.
2. The ABI-specific one-click command assets are AES-256-GCM authenticated self-decrypting ELF executables. Their command payloads use non-Garble builds for compatibility; the loader is Garble-obfuscated.

The public repository contains no source code, plaintext command payloads, release keys, signing private keys, or project state.
