# llm(1)

## Options

    -s, --system TEXT                                  # system prompt to use
    -m, --model NAME                                   # model to use
    -t, --template NAME                                # template to use
    --no-stream                                        # do not stream output
    -n, --no-log                                       # don't log to database
    -c, --continue                                     # continue the most recent conversation.
    --cid, --conversation ID                           # continue the conversation with the given ID.
    --key KEY                                          # API key to use
    --save NAME                                        # save prompt with this template name

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

    llm "Ten names for a cat"                                         # run a prompt using the default model
    llm -c "now for dogs"                                             # continue the last prompt
    cat myfile.py | llm -s "Explain this code"                        # run a system prompt against a file
    llm -a scanned-document.jpg "extract text"                        # extract text from an image (only with OpenAI model)
    llm -f https://example.com/article 'bullet point summary'         # summarize resource via URL
    llm -f /path/to/file 'bullet point summary'                       # summarize file

    llm -m NAME "Ten names for a cat"                                 # use a specific model

    curl -s https://www.nytimes.com | strip-tags .story-wrapper | ttok -t 4000 | llm -s "summary bullet points" | md        # summarize a news page
    fd -e py | files-to-prompt | llm -s "Act as a Python developer and do a code review" | md                               # code review with files provided in user prompt

