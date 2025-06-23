# Cache

![alt text](<../assets/Screenshot from 2025-06-16 12-32-05.png>)

[actions/cache](https://github.com/actions/cache)


```yaml
jobs:
  install:
    runs-on: ubuntu-latest
    steps:
      # ...
      - name: Cache Dependencies
        id: node-modules  
        uses: actions/cache@v4
        with:
          path: node_modules
          key: node-modules-${{ hashFiles('**/package-lock.json') }}
      - name: Install dependenceies
        if: steps.node-modules.outputs.cache-hit != 'true'
        run: npm ci
  use:
    needs: install
    runs-on: ubuntu-latest
    steps:
      # ...
      - name: Use Cached Dependencies
        id: node-modules  
        uses: actions/cache@v4
        with:
          path: node_modules
          key: node-modules-${{ hashFiles('**/package-lock.json') }}
```