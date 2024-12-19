**Running a Salt State**
```
salt <host> state.apply <env>.<host>
```

**Applying a command from a Salt State**
```
salt <host> state.sls_id <salt state name> <env>.<host>
```