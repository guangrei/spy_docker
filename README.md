[![Status CI](https://github.com/guangrei/spy_docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/guangrei/spy_docker/actions)

```
docker pull ghcr.io/guangrei/spy_docker/spylang
```

## Pytest

run the test suite with command:

```
docker run --rm -it ghcr.io/guangrei/spy_docker/spylang pytest
```

## Work with local `.spy` scripts

create file `test.spy` in current working directory:

```python
#! -*- mode: python -*-

def main() -> void:
    print("OK")
```

run command:

```
docker run --rm -it -v $(pwd):/spy/scripts ghcr.io/guangrei/spy_docker/spylang spy scripts/test.spy
```

compile to executable:

```
docker run --rm -it -v $(pwd):/spy/scripts ghcr.io/guangrei/spy_docker/spylang spy -c -t native scripts/test.spy
```

run compiled executable:

```
docker run --rm -it -v $(pwd):/spy/scripts ghcr.io/guangrei/spy_docker/spylang ./scripts/test
```

author: guangrei.
