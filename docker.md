# Docker

## Mount Current Directory

In Linux:
```
docker run --rm -it -v $(pwd):/build <program>
```

In PowerShell:
```
docker run --rm -it -v ${PWD}:/build <program>
```

Where `<program>` e.g. `<mono>`.
