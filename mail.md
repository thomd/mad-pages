
# mail(1)

### Sending Mail

  Message in a file `message.txt`:

    mail -s "subject" thomduerr@gmail.com < message.txt

  Interactively:

    mail -s "subject" thomduerr@gmail.com
      ... write ...
      ... finish and send with CTRL-D

