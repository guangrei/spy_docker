[![Docker pulls](https://img.shields.io/docker/pulls/phpid/spylang.svg )](https://hub.docker.com/r/phpid/spylang)


```
docker pull phpid/spylang
```

## pytest

run the test suite with command:

```
docker run --rm -it phpid/spylang pytest
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
docker run --rm -it -v $(pwd):/spy/scripts phpid/spylang spy scripts/test.spy
```

compile to executable:

```
docker run --rm -it -v $(pwd):/spy/scripts phpid/spylang spy -c -t native scripts/test.spy
```

run compiled executable:

```
docker run --rm -it -v $(pwd):/spy/scripts phpid/spylang ./scripts/test
```

author: guangrei.
