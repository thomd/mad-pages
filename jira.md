# jira(1)

    jira issue list -a $(jira me) -s "In Development"
    jira issue list -s ~Closed -s ~Cancelled -a $(jira me)          # issues assigned to me other than Closed or Cancelled
    jira issue list -q 'fixVersion = "1.17.3"' --plain              # list all tickets assigned to a release (fixed version)
