# Krypton + DeepSeek Quickstart

`deepseek-chat` and `deepseek-reasoner` are built into the default model catalog (`crates/codegen/xai-grok-models/default_models.json`) using DeepSeek's OpenAI-compatible Chat Completions endpoint (`https://api.deepseek.com/v1`).

## 1. Set your DeepSeek API key

```sh
export DEEPSEEK_API_KEY="sk-..."
```

Because both built-in DeepSeek models declare `env_key = "DEEPSEEK_API_KEY"`, setting this environment variable automatically enables BYOK mode and bypasses interactive `grok.com` browser login.

## 2. Launch with DeepSeek

One-off run:

```sh
cargo run -p xai-grok-pager-bin -- -m deepseek-chat
```

Or headless single-turn test:

```sh
cargo run -p xai-grok-pager-bin -- -m deepseek-chat -p "Say hello from Krypton + DeepSeek"
```

## 3. Make DeepSeek your persistent default

Add to `~/.grok/config.toml`:

```toml
[models]
default = "deepseek-chat"
```

Switch between `deepseek-chat` and `deepseek-reasoner` anytime inside the TUI via `/model deepseek-reasoner` or `Ctrl+M`.
