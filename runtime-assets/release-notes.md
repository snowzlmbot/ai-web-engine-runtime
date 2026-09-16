# AI Web Engine v1.3.5 — one-click Shell runtime

This release updates only the signed one-click command runtime (four ABI engines and encrypted init/start/stop/rollback containers). **APK development and publication remain paused. No APK is built or published in this release.**

- Unreadable encrypted histories no longer prevent listing valid sessions or creating a new session. Original ciphertext and the master key are preserved. This does not recover content encrypted with a lost/different key.
- No model provider is bundled. Save multiple providers with separate keys, select a provider and model in a conversation, then click Apply to current session. Other sessions remain unchanged.
- Duplicate or Unicode display names receive distinct internal IDs. Deleted session providers require explicit reselection rather than silent routing to another endpoint.

Startup checks only the remote version when there is no update. Invalid local script bundles are repaired through a checksum-checked full initialization; existing configuration, provider keys, sessions, skills and logs are preserved.
