# Conceitos

## Workflows

fica em um dado repositório onde é disparado por eventos
contêm um ou mais `jobs`

## Jobs

contêm um ou mais steps
rodam em paralelo por padrão
sempre tem que definir um `runner`

Runner -> every job gets its own runner

## Steps


![jobs](<../assets/Screenshot from 2025-06-13 13-51-11.png>)

## sintaxe básica:

```yaml
name: nome-opcional-do-workflow

on: event  # evento que dispara o workflow

jobs:                      # job
  nome-do-job:
    runs-on: ubuntu-latest # runner
    steps:                 # steps
      - name: step-name
        run: echo "a shell script or action"
      - name: step-name
        run: echo "are executed in order!"
```
