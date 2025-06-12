# hello-actions

## hello

```yaml
name: hello-actions
on: push

jobs:
  hello-action-job:
    runs-on: ubuntu-latest
    steps:
      - name: hello-step
        run: echo "Hello GitHubActions!"
```

sintaxe básica:

```txt
name: um-nome-opcional

on: event  # trigger

jobs:
  nome-do-job
  ...
```

[github-event-types](https://docs.github.com/en/rest/using-the-rest-api/github-event-types)
