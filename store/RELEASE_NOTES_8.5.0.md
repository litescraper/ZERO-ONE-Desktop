# ZERO ONE 8.5.0 source update

Automatic free AI in the encrypted API Vault uses OpenRouter's free-model router with your own key. It rejects paid model IDs, sends zero prompt/completion/request price ceilings, disables paid fallback and stops with a clear error when a free route is unavailable. The router chooses a free model automatically; an explicit available `:free` ID can also be saved.

The Vault adds normal OpenRouter, current Meta Model API, DeepSeek and Mistral profiles. New provider forms show account/key links and cost/privacy guidance. All saved chat profiles share the existing Assistant, ZeroThink Chat, Research and Agent adapter. Completion results retain the actual provider-reported model when supplied, so routed answers can identify the selected model.

Existing profiles and local CPU defaults are preserved. Keys remain encrypted by the operating system and stay out of renderer snapshots. The source update introduces no publisher account or database dependency. Free service availability and quotas remain provider-controlled.

OpenZero Gemma4 E2B remains the recommended lightweight CPU model. The app blocks the rejected Fusion model from the recommended setup; the new cloud options do not change local model provenance or terms.

This file describes source changes. It is not a Microsoft Store submission, certification receipt, public installer release or installed-version check.
