# Cancelling ans Skipping

## Cancelling

By default:
- get cancelled if jobs fail
- failed if at least one step fails
You can cancel manually (por exemplo clicando no botão)

## Sckipping

By default, all matching events start a workflow
Exceptions for `push` and `pull_request`: won't be triggered if `[skip actions]` and [similars](https://docs.github.com/en/actions/managing-workflow-runs-and-deployments/managing-workflow-runs/skipping-workflow-runs) commit message

```zsh
git commit -m "chore: change stuff [skip ci]"
```