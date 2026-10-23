# ZERO ONE Desktop 8.5.0 reviewer notes

Product 9PMPR7PTW025. AppX 8.5.0.0 x64. Identity `talktoai.ZEROONEDesktop`, publisher `CN=9B704446-6F62-4D52-954E-775436315422`.

Package: `ZERO-ONE-8.5.0-win-x64.appx`, 217,078,915 bytes. SHA-256: `c433363dec9d71db49c9da45a0df2e3940d046b71d01fe53cecdda211593f2f9`.

## Changes and optional API review

8.5 adds Automatic free AI through OpenRouter, normal OpenRouter, Meta Model API, DeepSeek and Mistral to the OS-encrypted API Vault. Open ZeroThink, then Tools & settings, then API Vault. The new-profile form starts on Automatic free AI. Saving a profile encrypts it and makes no API request; choose Make active to use it. The selected chat profile drives Assistant, ZeroThink Chat/Research, Agent and Browser Pilot planning.

Use the reviewer's own provider account and key for optional live cloud testing. No publisher credentials are supplied or required for the local app. Leave the free profile model empty for `openrouter/free`, or choose a currently available `:free` model. Paid model IDs are rejected before network transport. Each free-only request sets zero prompt/completion/request price ceilings and disables fallback. Quota or availability failures stop with an explicit error; no paid profile is attempted. Free quotas, model availability and host retention depend on the provider/account. A separate normal OpenRouter profile can explicitly choose paid models. Cloud calls send the relevant question, conversation and selected excerpts to the chosen service; the free router also uses its chosen model host.

The Meta option uses the current official Meta Model API, not the former Llama preview endpoint. Model IDs remain editable for account/catalog changes. Saved keys never appear in renderer snapshots. Changing provider or endpoint cannot silently transfer an existing key. No new login, publisher account, database or bundled private research is introduced.

## Account-free local review

Notes, offline research, local quantum and requested ZSEC scans require no cloud key, publisher account, payment or AI weights. Continue without a model starts no model download. Create/edit a ZNote, switch views and reopen it. Import a benign small text/PDF source, select it, choose Research and disable Use selected model, then run an offline evidence map and export a report. Source references and fingerprints are review aids, not scientific validation. Saved research projects retain selected evidence and completed reports; importing a project launches no actions. Exports contain readable selected content.

Optional built-in CPU setup reviews model terms, downloads pinned/hash-verified 3,416,119,872-byte OpenZero Gemma4 E2B weights, and configures the bundled local engine. At least 8 GB RAM is required; no GPU, API key or separate Ollama installation is required. Inspect download progress, cancel/retry and verification/loading state. Local inference is authenticated loopback. The Store edition does not install external Ollama and app updates remain Microsoft-managed.

Agent requires a selected project and separate write/command approval; approved commands have ordinary user OS permissions. Browser Pilot requires an isolated-tab grant, stops after 12 steps and pauses on cross-site/consequential actions. Secret/payment/file/CAPTCHA input controls remain blocked. ZSEC scans start after a user-selected folder/request; it is supplementary selected-folder scanning, not a primary antivirus replacement. IonQ hardware requires separate explicit possible-cost approval; IBM is read-only discovery.

## Verification and delivery

69 Vitest tests and 251 backend tests passed, together with TypeScript/production build and pinned ZSEC/CPU runtime verification. The Store production app passed native launch/DOM, encrypted free-profile save/select/load/delete via real IPC, fresh CPU setup, isolated Browser Pilot and clean/incomplete ZSEC scan checks. All 211 AppX ZIP entries passed integrity, its Store distribution marker is present, and archived ASAR matches tested staging. These checks used synthetic credentials and sent no live provider inference request. Package capability is runFullTrust only.

The upload AppX is unsigned for Microsoft Store processing. Package preparation and local validation do not establish submission, certification, public delivery or installed acceptance. Public privacy policy: https://researchforumonline.github.io/OpenZero/zero-one-privacy.html; match it to the 8.5 source privacy disclosure before submission.

WACK 10.0.28000.2270 completed a full 24-test run against this exact 8.5.0.0 package with overall PASS. One optional Blocked executables test reports static process-launch API imports and executable-name strings in Electron/Chromium resources, the bundled Python/ZSEC scanner and llama runtime. These findings are retained; not every optional check passed. The app's project Agent explicitly asks for command approval, and its startup/scan/local-engine process launches are bounded application features. The static findings are not represented as proof that no blocked launch can occur; Store certification remains Microsoft's decision.
