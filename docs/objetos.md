# Objetos

## Needs

- steps do qual depende
- como podem ser _n_ preciso fazer `needs.step_name`

```yaml
secundos:
  needs: primus
  runs-on: ubuntu-latest
  steps:
    - name: Use output value
      run: ${{ needs.primus.outputs.name }}
```
