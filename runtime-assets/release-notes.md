# AI Web Engine v1.3.6 — one-click Shell runtime

This release updates only the signed one-click command runtime (four ABI engines and encrypted init/start/stop/rollback containers). **APK development and publication remain paused. No APK is built or published in this release.**

- Generated instruction deltas are retained in an ordered event log, so slow or reconnecting browsers no longer lose content or terminal events.
- Competing generation, legacy chat, update and delete operations for the same session now fail immediately instead of applying stale work later.
- ShortX canonicalization preserves large integers and high-precision decimals and rejects trailing JSON data.
- Existing unreadable-history isolation, per-provider keys and per-session provider selection remain intact. Original ciphertext, the master key and existing configuration are preserved.

Startup checks only the remote version when there is no update. Invalid local script bundles are repaired through a checksum-checked full initialization; existing configuration, provider keys, sessions, skills and logs are preserved.
