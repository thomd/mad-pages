# ollama(1)

    ollama serve

## Ollama with Open WebUI

    uvx --python 3.11 open-webui serve
    open http://localhost:8080

## Ollama Models

    ollama list                                                   # list local models
    ollama show MODEL                                             # show model information
    ollama pull MODEL                                             # pull a model or update a local model (only the diff will be pulled)
    ollama rm MODEL                                               # remove a model
    ollama ps                                                     # list models which are currently loaded
    ollama stop MODEL                                             # stop a model which is currently running

## Ollama Usage

    ollama run MODEL                                              # chat with a MODEL
    ollama run MODEL "Summarize this file: $(cat README.md)"      # pass prompt as an argument

## Customize with Chat Settings

  Start ollama chat session and set a system prompt and parameters:

    ollama run llama3.2
    /set system You are a helpful assistant.
    /set parameter temperature 1
    /set parameter num_ctx 4096
    /save my_model
    /bye

  Then use the customized `llama3.2` based model `my_model` with

    ollama run my_model

# Inspect Ollama with Mitmproxy

  start revers proxy

    mitmproxy --mode reverse:http://localhost:11434@11435

  start Ollama server

    OLLAMA_HOST=127.0.0.1:11434 ollama serve

  inspect llm requests in Mitmproxy

    export OLLAMA_HOST=127.0.0.1:11435
    llm --tool llm_time "What time is it?" --no-stream

