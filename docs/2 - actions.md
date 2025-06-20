## action:

- a "custom command";
- an application that performs a task (more complex than a command)

1. **Actions** = GitHub Actions
2. **actions** = custom command

![run x use](../assets/actions.png)

exemplo de repo [/actions/checkout](https://github.com/actions/checkout)

existe um [marketplace](https://github.com/marketplace/actions/checkout)


```yaml
steps:
  # não roda no repo, tenho que baixar a branch:
  - name: Get my stuff
    # https://github.com/actions/checkout
    # https://github.com/marketplace/actions/checkout
    uses: actions/checkout@v4
    with: # para passar parâmetros para o use
      repository: "if-not-the-same" # nesse caso é opcional
```