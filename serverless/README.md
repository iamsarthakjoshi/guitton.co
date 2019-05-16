# Python SES Contact Form

[![serverless](http://public.serverless.com/badges/v3.svg)](http://www.serverless.com)

AWS SES using Serverless Framework written in Python

## Serverless Framework Setup

| **Command**                                  | **Description**                                                                         |
| -------------------------------------------- | --------------------------------------------------------------------------------------- |
| `npm install -g serverless`                  | Install Serverless CLI                                                                  |
| `npm install`                                | Install Serverless dependencies                                                         |
| Set up an AWS account with admin permissions | [Documentation](https://serverless.com/framework/docs/providers/aws/guide/credentials/) |

## How to Deploy

```bash
cd serverless
npm install
sls deploy -v
```

## Service Endpoints

The service exposes 1 REST API endpoints:

| **Endpoint**     | **Description**                   | **Parameters**                                                                             |
| ---------------- | --------------------------------- | ------------------------------------------------------------------------------------------ |
| `POST /sendMail` | Submit the data from contact form | `{"firstname": "John", "lastname": "Doe", "email": "john@doe.com", "message": "Hi there"}` |

## Invocation

```bash
curl ---header "Content-Type: application/json" \
	--request POST \
	--data '{"firstname": "John", "lastname": "Doe", "email": "john@doe.com", "message": "Hi there"}'\
	https://02e7mhsl5f.execute-api.eu-central-1.amazonaws.com/development/sendMail

```

# `sls` or `serverless` CLI Usage

### `deploy function` command

Deploy only one function:

    sls deploy function -f <function-name> -v

### `invoke` command

Run a specific function with a provided input and get the logs

    sls invoke -f <function-name> -p event.json -l

Run a specific function without input and get the logs

    sls invoke -f <function-name> -l

### `logs` command

Tail the logs of a function:

    sls logs -f <function-name> -t

### `info` command

Information about the service (stage, region, endpoints, functions):

    sls info

### `help` command

Just use it on anything:

    sls  help

or

    sls <command> --help
