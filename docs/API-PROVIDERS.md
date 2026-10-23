# API providers and automatic free AI

The 8.5.0 source adds five Vault choices: Automatic free AI (OpenRouter), OpenRouter, Meta Model API, DeepSeek and Mistral. Existing local CPU inference and saved profiles remain available. The selected Vault chat profile powers Assistant, ZeroThink Chat, Research, Agent planning and Browser Pilot planning.

## Use automatic free AI

1. Open ZeroThink, then API Vault. The new-profile form starts on Automatic free AI.
2. Open the OpenRouter keys page from the form, create your own key and paste it in the password field. Saving stores it under operating-system encryption; it makes no API call.
3. Leave Model empty to use `openrouter/free`, or enter a currently available OpenRouter model ID ending in `:free`.
4. Save the profile and choose Make active. New requests use that profile; existing saved conversations and sources remain local.

OpenRouter selects an available free model for `openrouter/free`; the model can change between requests. A named `:free` model pins the selected free variant when it is available. Free requests are subject to account access, quotas, capacity and rate limits. The app does not supply a publisher key, create accounts, rotate accounts to evade quotas or promise unlimited access.

The free-only adapter rejects paid model IDs and automatic paid-routing aliases before transport. Each request sends `provider.max_price` with prompt, completion and request prices all zero, and `allow_fallbacks: false`. There is no paid model list, paid plugin or cross-provider retry. An unavailable route, exhausted quota or provider error stops the request and reports that no paid fallback was attempted. Unknown transport/provider error bodies are redacted. The normal OpenRouter profile permits user-chosen paid IDs; it is a separate explicit choice.

Automatic free AI is an opt-in cloud profile. Prompts, selected source excerpts and relevant conversation context are sent to OpenRouter and its selected model host under their terms. Keep sensitive research in local/offline mode when cloud processing is unsuitable. Selecting free AI does not automatically change another saved or local profile.

## Provider choices

| Profile | Official chat endpoint | Initial model | Cost behavior |
| --- | --- | --- | --- |
| Automatic free AI | `https://openrouter.ai/api/v1/chat/completions` | `openrouter/free` | Free-only IDs and zero-price ceilings; stops on failure |
| OpenRouter | `https://openrouter.ai/api/v1/chat/completions` | `openrouter/free` | User may choose a paid model |
| Meta Model API | `https://api.meta.ai/v1/chat/completions` | `muse-spark-1.3` | User account access and billing |
| DeepSeek | `https://api.deepseek.com/chat/completions` | `deepseek-flash` | User account access and billing |
| Mistral AI | `https://api.mistral.ai/v1/chat/completions` | `mistral-small-latest` | User account access and billing |

The current Meta integration uses Meta Model API. Llama models can also be accessed through Groq, OpenRouter or a user-owned compatible server. Model IDs are editable because provider catalogs change. Provider credentials are bound to fixed official endpoints; changing to another provider does not silently transfer a saved key. Custom endpoints are available only through the user-owned compatible-server profile, with HTTPS required remotely.

Gemini, Groq and other services may offer account-specific free plans or credits, but the app cannot infer the billing state of an arbitrary saved key. They are not automatic fallbacks from the free-only profile. The free router is the only new automatic cloud selection path.

Official references checked 23 October 2026: [OpenRouter free router](https://openrouter.ai/docs/guides/routing/routers/free-router), [OpenRouter provider price caps](https://openrouter.ai/docs/guides/routing/provider-selection#max-price), [Meta chat completions](https://dev.meta.ai/docs/protocols/chat-completions), [DeepSeek API](https://api-docs.deepseek.com/api/responses), [Mistral API](https://docs.mistral.ai/api). Provider documentation establishes the transport contract; mock tests do not establish live account eligibility or a successful billable inference.
