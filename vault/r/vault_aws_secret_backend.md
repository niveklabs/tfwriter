# vault_aws_secret_backend

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vault_aws_secret_backend" {
  source = "./modules/vault/r/vault_aws_secret_backend"

  # access_key - (optional) is a type of string
  access_key = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # path - (optional) is a type of string
  path = null
  # region - (optional) is a type of string
  region = null
  # secret_key - (optional) is a type of string
  secret_key = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key" {
  description = "(optional) - The AWS Access Key ID to use when generating new credentials."
  type        = string
  default     = null
}

variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "path" {
  description = "(optional) - Path to mount the backend at."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The AWS region to make API calls against. Defaults to us-east-1."
  type        = string
  default     = null
}

variable "secret_key" {
  description = "(optional) - The AWS Secret Access Key to use when generating new credentials."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_secret_backend" "this" {
  # access_key - (optional) is a type of string
  access_key = var.access_key
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  # description - (optional) is a type of string
  description = var.description
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = var.max_lease_ttl_seconds
  # path - (optional) is a type of string
  path = var.path
  # region - (optional) is a type of string
  region = var.region
  # secret_key - (optional) is a type of string
  secret_key = var.secret_key
}
```

[top](#index)

### Outputs

```terraform
output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_aws_secret_backend.this.default_lease_ttl_seconds
}

output "id" {
  description = "returns a string"
  value       = vault_aws_secret_backend.this.id
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_aws_secret_backend.this.max_lease_ttl_seconds
}

output "region" {
  description = "returns a string"
  value       = vault_aws_secret_backend.this.region
}

output "this" {
  value = vault_aws_secret_backend.this
}
```

[top](#index)