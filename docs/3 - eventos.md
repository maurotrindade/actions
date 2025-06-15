# Events

- posso usar _n_ eventos por workflows
- [events that trigger workflows](https://docs.github.com/pt/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows)

## exemplo:

```yaml
on:
  pull_request:        # event 1
    types: [opened]    # activity types
    branches:           # filters
      - main
      - 'feat-*'
      - '!chore/**' # one or more / too
    paths: ['**.md']
  workflow_dispatch: # event 1
```

## Activity Types

atributos opcionais de alguns eventos para afunilar

![exemplo pull_request](<../assets/Screenshot from 2025-06-15 10-21-36.png>)

se uso só o nome do evento o comportamento normalmente é chamar somente um ou alguns dos types. Exemplo nesse caso são `opened`, `synchronize` ou `reopened` (ou seja os outros são ignorados).s

## Filters

somente alguns poucos eventos tem filtros

```txt
push:
  branches | branches-ignore| tags | tags-ignore
  path | path-ignore
```
