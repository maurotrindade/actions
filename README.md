# GitHub Actions

- **workflow** automation service;
- automate **all kinds** of repository-related processes;
- CI/CD is no of many possible workflows

## workflows

- when something happens IN or TO yout repository (Events);
- automactic ACTIONS are executed in response

## resources

- [starter-workflows](https://github.com/actions/starter-workflows)
- [github-actions-course-resources](https://github.com/academind/github-actions-course-resources/tree/main/Code)

- [events-that-trigger-workflows](https://docs.github.com/pt/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows)

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

[conceitos básicos](docs/1%20-%20conceitos%20básicos)

[actions](docs/2%20-%20actions.md)