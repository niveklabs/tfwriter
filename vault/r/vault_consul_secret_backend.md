# vault_consul_secret_backend

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_consul_secret_backend" {
  source = "./modules/vault/r/vault_consul_secret_backend"

  # address - (required) is a type of string
  address = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # path - (optional) is a type of string
  path = null
  # scheme - (optional) is a type of string
  scheme = null
  # token - (required) is a type of string
  token = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required) - Specifies the address of the Consul instance, provided as \"host:port\" like \"127.0.0.1:8500\"."
  type        = string
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
  description = "(optional) - Unique name of the Vault Consul mount to configure"
  type        = string
  default     = null
}

variable "scheme" {
  description = "(optional) - Specifies the URL scheme to use. Defaults to \"http\"."
  type        = string
  default     = null
}

variable "token" {
  description = "(required) - Specifies the Consul ACL token to use. This must be a management type token."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_consul_secret_backend" "this" {
  address                   = var.address
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  description               = var.description
  max_lease_ttl_seconds     = var.max_lease_ttl_seconds
  path                      = var.path
  scheme                    = var.scheme
  token                     = var.token
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_consul_secret_backend.this.id
}

output "this" {
  value = vault_consul_secret_backend.this
}
```

[top](#index)