# AI Web Engine v1.3.4 — one-click Shell runtime

This release updates only the signed one-click command runtime (four ABI engines and encrypted init/start/stop/rollback containers). **No new APK is built or published.** The last APK release remains v1.3.3: https://github.com/snowzlmbot/ai-web-engine-runtime/releases/tag/v1.3.3

Startup checks only the remote version when there is no update. Invalid local script bundles are repaired through a checksum-checked full initialization; existing configuration, provider keys, sessions, skills and logs are preserved.
