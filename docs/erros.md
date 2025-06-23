# Erros

```yaml
jobs:
  error:
    runs-on: ubuntu-latest
    steps:
      - name: Pass
        id: erroed-step  # para ser referenciado no if
        run: exit 0
      - name: Everything is fine
        run: exit 1
      - name: I never run
        run: echo "I realy never run"
```

## jobs que depende de um que falhou vão ser cancelados

o mesmo ocorre se dependender indiretamente

```yaml
canceled:
  needs: error  # depende de error, será cancelado
  runs-on: ubuntu-latest
  steps:
    - name: Pass
      run: echo "I will never run"
```

## jobs que não tem relação com o que falhou executam normalmente

não tem relação e não depende direta ou indiretamente

```yaml
runs:
  # não tem relação com erro, vai ser executado normalmente
  runs-on: ubuntu-latest
  steps:
    - name: Everything is fine
      continue-on-error: true # esse step pode falhar
      run: exit 1
    - name: Continue on error
      run: echo "Continue on error"
```
