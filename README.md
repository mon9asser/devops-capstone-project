# devops-capstone-project

![Build Status](https://github.com/mon9asser/devops-capstone-project/actions/workflows/ci-build.yaml/badge.svg)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

## Description

This repository contains the customer accounts microservice for an e-commerce platform, built as part of the IBM DevOps and Software Engineering Professional Certificate Capstone Project. The service provides a RESTful API to **create, read, update, delete, and list** customer accounts, storing basic customer information such as name and address. It is built with Python and Flask, following the Model-View-Controller pattern, and is designed to be containerized with Docker and deployed to Kubernetes as part of a full CI/CD pipeline.

## Development Environment

These labs are designed to be executed in the IBM Developer Skills Network Cloud IDE with OpenShift.

Initialize the environment by sourcing the setup script (do **not** run it as a bash script — it must be sourced so it can set environment variables):

```bash
source bin/setup.sh
```

This installs Python 3.9, sets it as the default, modifies the bash prompt, and creates and activates a Python virtual environment. After sourcing, your prompt should look like:

```bash
(venv) theia:project$
```

## Useful Commands

### Activate the Python 3.9 virtual environment

```bash
source ~/venv/bin/activate
```

### Install Python dependencies

```bash
make install
```

### Start the Postgres Docker container

```bash
make db
```

Use `docker ps` to confirm Postgres is running.

## Project Layout

```text
├── service         <- microservice package
│   ├── common/     <- common log and error handlers
│   ├── config.py   <- Flask configuration object
│   ├── models.py   <- code for the persistent model
│   └── routes.py   <- code for the REST API routes
├── setup.cfg       <- tools setup config
└── tests                       <- folder for all of the tests
    ├── factories.py            <- test factories
    ├── test_cli_commands.py    <- CLI tests
    ├── test_models.py          <- model unit tests
    └── test_routes.py          <- route unit tests
```

## Data Model

The Account model contains the following fields:

| Name | Type | Optional |
|------|------|----------|
| id | Integer | False |
| name | String(64) | False |
| email | String(64) | False |
| address | String(256) | False |
| phone_number | String(32) | True |
| date_joined | Date | False |

## Project Status

The `CREATE` endpoint is implemented. This project's goal is to add the `READ`, `UPDATE`, `DELETE`, and `LIST` REST API endpoints while maintaining 95% code coverage, followed by containerizing the service with Docker and deploying it to Kubernetes.

## License

Licensed under the Apache License. See [LICENSE](LICENSE)

## © IBM Corporation 2022. All rights reserved.
