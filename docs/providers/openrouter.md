---
description: Configure OpenRouter in Roo Code to access 100+ language models from various providers through a single API with automatic model discovery.
keywords:
  - roo code
  - openrouter
  - ai provider
  - language models
  - api configuration
  - model selection
  - prompt caching
  - byok
sidebar_label: OpenRouter
image: /img/social-share.jpg
---

# Using OpenRouter With Roo Code

OpenRouter is an AI platform that provides access to a wide variety of language models from different providers, all through a single API.  This can simplify setup and allow you to easily experiment with different models.

**Website:** [https://openrouter.ai/](https://openrouter.ai/)

---

## Getting an API Key

1.  **Sign Up/Sign In:** Go to the [OpenRouter website](https://openrouter.ai/).  Sign in with your Google or GitHub account.
2.  **Get an API Key:** Go to the [keys page](https://openrouter.ai/keys).  You should see an API key listed.  If not, create a new key.
3.  **Copy the Key:** Copy the API key.

---

## Supported Models

OpenRouter supports a large and growing number of models.  Roo Code automatically fetches the list of available models. Refer to the [OpenRouter Models page](https://openrouter.ai/models) for the complete and up-to-date list.

---

## Configuration in Roo Code

1.  **Open Roo Code Settings:** Click the gear icon (<Codicon name="gear" />) in the Roo Code panel.
2.  **Select Provider:** Choose "OpenRouter" from the "API Provider" dropdown.
3.  **Enter API Key:** Paste your OpenRouter API key into the "OpenRouter API Key" field.
4.  **Select Model:** Choose your desired model from the "Model" dropdown.
5.  **(Optional) Custom Base URL:** If you need to use a custom base URL for the OpenRouter API, check "Use custom base URL" and enter the URL. Leave this blank for most users.

---

## Supported Transforms

OpenRouter provides an [optional "middle-out" message transform](https://openrouter.ai/docs/features/message-transforms) to help with prompts that exceed the maximum context size of a model. You can enable it by checking the "Compress prompts and message chains to the context size" box.

---

## Tips and Notes

* **Model Selection:** OpenRouter offers a wide range of models. Experiment to find the best one for your needs.
* **Pricing:**  OpenRouter charges based on the underlying model's pricing.  See the [OpenRouter Models page](https://openrouter.ai/models) for details.
*   **Prompt Caching:**
    *   OpenRouter passes caching requests to underlying models that support it. Check the [OpenRouter Models page](https://openrouter.ai/models) to see which models offer caching.
    *   For most models, caching should activate automatically if supported by the model itself (similar to how Requesty works).
    *   **Models with prompt caching support include:**
        *   Anthropic Claude Sonnet 3.5, 3.7
        *   Anthropic Claude Haiku 3.5
        *   **Anthropic Claude Haiku 4.5** (newly added)
        *   Google Gemini models (with manual activation - see below)
    *   **Exception for Gemini Models via OpenRouter:** Due to potential response delays sometimes observed with Google's caching mechanism when accessed via OpenRouter, a manual activation step is required *specifically for Gemini models*.
    *   If using a **Gemini model** via OpenRouter, you **must manually check** the "Enable Prompt Caching" box in the provider settings to activate caching for that model. This checkbox serves as a temporary workaround. For non-Gemini models on OpenRouter, this checkbox is not necessary for caching.
*   **Bring Your Own Key (BYOK):** If you use your own key for the underlying service, OpenRouter charges 5% of what it normally would. Roo Code automatically adjusts the cost calculation to reflect this.
