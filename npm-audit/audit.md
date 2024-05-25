### denial of service

- regex
- memory exhaustion
- event loop blocking

### misc

- timing attack
- prototype attack

## CLI commands

```
npm audit > result.txt
```

```
npm audit | awk '/Hight/ { print $0}'
```

```
npm audit --json > result.json
```

```
npm list --depth 0

npm audit fix --package-lock-only

--dry-run
--only=dev|prod   === --production
--force


```
