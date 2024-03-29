# github-contributions
[![Build](https://github.com/soda480/github-contributions/actions/workflows/main.yml/badge.svg)](https://github.com/soda480/github-contributions/actions/workflows/main.yml)
[![Code Grade](https://api.codiga.io/project/21990/status/svg)](https://app.codiga.io/public/project/21990/github-contributions/dashboard)
[![complexity](https://img.shields.io/badge/complexity-Simple:%205-green)](https://radon.readthedocs.io/en/latest/api.html#module-radon.complexity)
[![vulnerabilities](https://img.shields.io/badge/vulnerabilities-None-green)](https://pypi.org/project/bandit/)
[![python](https://img.shields.io/badge/python-3.6-teal)](https://www.python.org/downloads/)

A Python script to get contribution metrics for all members of a GitHub organization. The script utilizes the GitHub GraphQL API, exports, sorts, and writes the report to a csv file.

## `ghcontrib`
```bash
usage: ghcontrib [-h] [--org ORG]

A Python script to get contribution metrics for all members of a GitHub
organization using the GitHub GraphQL API

optional arguments:
  -h, --help  show this help message and exit
  --org ORG   GitHub organization containing members to process
  ```

Build the Docker image:
```bash
docker image build \
--build-arg http_proxy \
--build-arg https_proxy \
-t ghcontrib:latest .
```

Run the Docker container:
```bash
docker container run \
--rm \
-it \
-e http_proxy \
-e https_proxy \
-v $PWD:/ghcontrib \
ghcontrib:latest /bin/sh
```

Export the required environment variable and execute the script:
```bash
export GH_TOKEN_PSW=--github-token--
ghcontrib --org edgexfoundry
```

![preview](https://raw.githubusercontent.com/soda480/github-contributions/master/docs/images/contributions.gif)
