# llm(1)

## Prompts

    llm -s 'extract text as markdown' -a image.png
    llm -s 'summarize text' -f file.txt

## Templates

    curl -L https://llm.datasette.io/ | llm -t gh:simonw/summarize
    git diff --cached | llm -t gh:thomd/commit-message

# Examples

    defuddle parse https://example.com/page.html --markdown | llm -s 'summarize this text in one paragraph'
