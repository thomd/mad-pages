# jira(1)

    jira issue list -a $(jira me) -s "In Development"
    jira issue list -s ~Closed -s ~Cancelled -a $(jira me)          # issues assigned to me other than Closed or Cancelled
