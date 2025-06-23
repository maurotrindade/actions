# Conceitos

![jobs](<../assets/Screenshot from 2025-06-13 13-51-11.png>)

## Workflows

- ficam em um dado repositório onde são disparados por eventos
- contêm um ou mais `jobs`

## Jobs

- contêm um ou mais steps
- rodam em paralelo por padrão
- cada um tem seu próprio `runner`
- podem ser condicionais

## Steps

- executam shell script (`run`)
- podem ser actions (`uses`)
- são executados em órdem
- podem ser condicionais

## sintaxe básica:

```yaml
# name é opcional
# - se não existe vai ser o nome do arquivo;
# - se repetido vai aparecer duas vzs no menu (nome do arquivo diferencía);
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
