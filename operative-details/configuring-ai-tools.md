---
icon: copilot
order: 900
---

We use three main AI helpers at DataWars:

* [`continue.dev`](https://docs.continue.dev/) for VSCode
* `sgpt` for command line help
* `jupyter-ai`

Private API Keys to setup AI are located in the [following document](https://docs.google.com/spreadsheets/d/1_98O2y8Qss4jvJadHo8Y7LLIoAdr785Rp7-zn9f35SA/edit?gid=0#gid=0)

!!!danger Danger
Don't share the API Keys with ANYBODY. This is highly sensitive information.
!!!


### Setting up `continue.dev`

If you have any doubts, go to the [Continue docs](https://docs.continue.dev/)

Here's a quick setup guide:

[!embed](https://www.loom.com/embed/3cbbd4bce27e44568ec3dea6fb7ebf95?sid=20008dcc-0856-4a98-87e4-02c964aab6cb)

For the most part, you can use the `gpt-4o-mini`, as it's a fast, effective and cheap model. For more advanced tasks you can use `gpt-4o`, but it's more expensive. Use it with discretion.

The config file for continue.dev will look something like:

```json
{
  "tabAutocompleteModel": {
    "apiKey": "API Key",
    "title": "Codestral",
    "model": "codestral-latest",
    "provider": "mistral",
    "apiBase": "https://api.mistral.ai/v1"
  },
  "models": [
    {
      "model": "gpt-4o-mini",
      "title": "GPT-4o Mini",
      "systemMessage": "You are an expert software developer. You give helpful and concise responses.",
      "apiKey": "API KEY",
      "provider": "openai"
    },
    {
      "model": "gpt-4o",
      "title": "GPT-4o",
      "systemMessage": "You are an expert software developer. You give helpful and concise responses.",
      "apiKey": "API KEY",
      "provider": "openai"
    }
  ],
  "contextProviders": [
    // The rest of the confs...
  ],
  "slashCommands": [
    // other confs...
  ],
  "data": []
}
```

### SGPT

SGPT docs: https://github.com/TheR1D/shell_gpt

SGPT is very simple to install, just `pip install shell-gpt`.

Here's a quick start guide:

[!embed](https://www.loom.com/embed/1f6d7fd679d94d91a57e78b0ed514d61?sid=cc3b0bfa-0c1f-4add-b434-b27fc480d124)
