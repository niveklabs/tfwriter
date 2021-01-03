# vault_mount

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
module "vault_mount" {
  source = "./modules/vault/r/vault_mount"

  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # external_entropy_access - (optional) is a type of bool
  external_entropy_access = null
  # local - (optional) is a type of bool
  local = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # options - (optional) is a type of map of string
  options = {}
  # path - (required) is a type of string
  path = null
  # seal_wrap - (optional) is a type of bool
  seal_wrap = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for tokens and secrets in seconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount"
  type        = string
  default     = null
}

variable "external_entropy_access" {
  description = "(optional) - Enable the secrets engine to access Vault's external entropy source"
  type        = bool
  default     = null
}

variable "local" {
  description = "(optional) - Local mount flag that can be explicitly set to true to enforce local mount in HA environment"
  type        = bool
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for tokens and secrets in seconds"
  type        = number
  default     = null
}

variable "options" {
  description = "(optional) - Specifies mount type specific options that are passed to the backend"
  type        = map(string)
  default     = null
}

variable "path" {
  description = "(required) - Where the secret backend will be mounted"
  type        = string
}

variable "seal_wrap" {
  description = "(optional) - Enable seal wrapping for the mount, causing values stored by the mount to be wrapped by the seal's encryption capability"
  type        = bool
  default     = null
}

variable "type" {
  description = "(required) - Type of the backend, such as 'aws'"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_mount" "this" {
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  description               = var.description
  external_entropy_access   = var.external_entropy_access
  local                     = var.local
  max_lease_ttl_seconds     = var.max_lease_ttl_seconds
  options                   = var.options
  path                      = var.path
  seal_wrap                 = var.seal_wrap
  type                      = var.type
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_mount.this.accessor
}

output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_mount.this.default_lease_ttl_seconds
}

output "id" {
  description = "returns a string"
  value       = vault_mount.this.id
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_mount.this.max_lease_ttl_seconds
}

output "seal_wrap" {
  description = "returns a bool"
  value       = vault_mount.this.seal_wrap
}

output "this" {
  value = vault_mount.this
}
```

[top](#index)