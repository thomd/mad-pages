# llm(1)

## Options

    -s, --system TEXT                                # system prompt to use
    -m, --model NAME                                 # model to use
    -t, --template NAME                              # template to use
    --no-stream                                      # do not stream output
    -n, --no-log                                     # don't log to database
    -c, --continue                                   # continue the most recent conversation.
    --cid, --conversation ID                         # continue the conversation with the given ID.
    --key KEY                                        # API key to use
    --save NAME                                      # save prompt with this template name

## API Keys

    llm keys                                           # show keys
    llm keys path                                      # show path to the keys.json file
    llm keys set openai                                # paste your OpenAI API key into this
    llm keys get openai                                # paste your OpenAI API key into this

## Models

    llm models                                         # list available models and default model
    llm models default NAME                            # show or set the default model
    llm install llm-claude-3                           # install Anthropic models
    llm install llm-mistral                            # install Mistral models
    llm install llm-ollama

## Usage

    llm chat                                           # use llm in interactive chat modus
    llm -s "be a helpful assistant"                    # run a system prompt
    llm "ten names for a cat"                          # run a user prompt
    llm -c "now for dogs"                              # continue the last prompt

    llm "extract text" -a scanned-document.jpg         # extract text from an image

