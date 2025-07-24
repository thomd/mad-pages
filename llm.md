# llm(1)

## Inspect Ollama with Mitmproxy

  start revers proxy

    mitmproxy --mode reverse:http://localhost:11434

  start Ollama server

    OLLAMA_HOST=127.0.0.1:11434 ollama serve

  inspect llm requests in Mitmproxy

    export OLLAMA\_HOST=127.0.0.1:8080
    llm -m llama3.2 --tool llm_time "What time is it?" --no-stream

## Inspect OpenAI with Mitmproxy

    mitmproxy --mode reverse:https://api.openai.com
    export OPENAI\_BASE\_URL="http://localhost:8080/v1"
    llm -m 4o-mini --tool llm_time "What time is it?" --no-stream

## Inspect ANthropic with Mitmproxy

    mitmproxy --mode reverse:https://api.anthropic.com
    export ANTHROPIC_BASE_URL="http://localhost:8080"
    llm -m claude-3-sonnet) --tool llm_time "What time is it?" --no-stream
