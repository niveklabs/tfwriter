# vault_azure_access_credentials

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_azure_access_credentials" {
  source = "./modules/vault/d/vault_azure_access_credentials"

  # backend - (required) is a type of string
  backend = null
  # max_cred_validation_seconds - (optional) is a type of number
  max_cred_validation_seconds = null
  # num_seconds_between_tests - (optional) is a type of number
  num_seconds_between_tests = null
  # num_sequential_successes - (optional) is a type of number
  num_sequential_successes = null
  # role - (required) is a type of string
  role = null
  # validate_creds - (optional) is a type of bool
  validate_creds = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - Azure Secret Backend to read credentials from."
  type        = string
}

variable "max_cred_validation_seconds" {
  description = "(optional) - If 'validate_creds' is true, the number of seconds after which to give up validating credentials."
  type        = number
  default     = null
}

variable "num_seconds_between_tests" {
  description = "(optional) - If 'validate_creds' is true, the number of seconds to wait between each test of generated credentials."
  type        = number
  default     = null
}

variable "num_sequential_successes" {
  description = "(optional) - If 'validate_creds' is true, the number of sequential successes required to validate generated credentials."
  type        = number
  default     = null
}

variable "role" {
  description = "(required) - Azure Secret Role to read credentials from."
  type        = string
}

variable "validate_creds" {
  description = "(optional) - Whether generated credentials should be validated before being returned."
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vault_azure_access_credentials" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # max_cred_validation_seconds - (optional) is a type of number
  max_cred_validation_seconds = var.max_cred_validation_seconds
  # num_seconds_between_tests - (optional) is a type of number
  num_seconds_between_tests = var.num_seconds_between_tests
  # num_sequential_successes - (optional) is a type of number
  num_sequential_successes = var.num_sequential_successes
  # role - (required) is a type of string
  role = var.role
  # validate_creds - (optional) is a type of bool
  validate_creds = var.validate_creds
}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = data.vault_azure_access_credentials.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = data.vault_azure_access_credentials.this.client_secret
}

output "id" {
  description = "returns a string"
  value       = data.vault_azure_access_credentials.this.id
}

output "lease_duration" {
  description = "returns a number"
  value       = data.vault_azure_access_credentials.this.lease_duration
}

output "lease_id" {
  description = "returns a string"
  value       = data.vault_azure_access_credentials.this.lease_id
}

output "lease_renewable" {
  description = "returns a bool"
  value       = data.vault_azure_access_credentials.this.lease_renewable
}

output "lease_start_time" {
  description = "returns a string"
  value       = data.vault_azure_access_credentials.this.lease_start_time
}

output "this" {
  value = vault_azure_access_credentials.this
}
```

[top](#index)