# Vault-unsealer

This project aims to make it easier to automate the secure unsealing of a Vault
server.

## Usage

```
This is a CLI tool to help automate the setup and management of
Hashicorp Vault.

It will continuously attempt to unseal the target Vault instance, by retrieving
unseal keys from a KMS keyring.

Usage:
  vault-unsealer [command]

Available Commands:
  help        Help about any command
  init        Initialise the target Vault instance
  unseal      A brief description of your command

Flags:
      --aws-kms-key-id string                The ID or ARN of the AWS KMS key to encrypt values
      --aws-ssm-key-prefix string            The Key Prefix for SSM Parameter store
  -h, --help                                 help for vault-unsealer
      --mode string                          Select the mode to use 'aws-kms-ssm' => AWS SSM parameter store using AWS KMS encryption (default "aws-kms-ssm")
      --secret-shares int                    Total count of secret shares that exist (default 1)
      --secret-threshold int                 Minimum required secret shares to unseal (default 1)

Use "vault-unsealer [command] --help" for more information about a command.
```

## How to setup vault-unsealer via AWS KMS and SSM

[Instruction on existing and new vaults for unsealing vault using KMS and SSM](docs/aws-kms-ssm.md)

## Build from source

```bash
go get github.com/jetstack/vault-unsealer
make -C $(go env GOPATH)/src/github.com/jetstack/vault-unsealer build
```

## Build a Docker image

```bash
docker build -t vault-unsealer:<version> .
```
