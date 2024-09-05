# ai search

## Installation

### Load environment variables

```bash
# set path
$ export PYTHONPATH=.
$ cp .env.local .env
# set env
$ export $(cat .env | xargs) 2>/dev/null
```

### Install poetry

Requires `poetry` python package.

```bash
$ poetry install
$ poetry shell
```

### Direct execution
```bash
# for dev
$ uvicorn src.main:app --host 0.0.0.0 --port 38900 --reload
# for production
$ gunicorn -w 4 -k uvicorn.workers.UvicornWorker -b 0.0.0.0:8080 src.main:app
```

### Docker

```bash
$ docker build .
$ docker-compose up
```

### Testing

```sh
$ mypy .
```
