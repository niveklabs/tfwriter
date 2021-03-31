# vault_mfa_duo

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
module "vault_mfa_duo" {
  source = "./modules/vault/r/vault_mfa_duo"

  # api_hostname - (required) is a type of string
  api_hostname = null
  # integration_key - (required) is a type of string
  integration_key = null
  # mount_accessor - (required) is a type of string
  mount_accessor = null
  # name - (required) is a type of string
  name = null
  # push_info - (optional) is a type of string
  push_info = null
  # secret_key - (required) is a type of string
  secret_key = null
  # username_format - (optional) is a type of string
  username_format = null
}
```

[top](#index)

### Variables

```terraform
variable "api_hostname" {
  description = "(required) - API hostname for Duo."
  type        = string
}

variable "integration_key" {
  description = "(required) - Integration key for Duo."
  type        = string
}

variable "mount_accessor" {
  description = "(required) - The mount to tie this method to for use in automatic mappings. The mapping will use the Name field of Aliases associated with this mount as the username in the mapping."
  type        = string
}

variable "name" {
  description = "(required) - Name of the MFA method."
  type        = string
}

variable "push_info" {
  description = "(optional) - Push information for Duo."
  type        = string
  default     = null
}

variable "secret_key" {
  description = "(required) - Secret key for Duo."
  type        = string
}

variable "username_format" {
  description = "(optional) - A format string for mapping Identity names to MFA method names. Values to substitute should be placed in `{{}}`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_mfa_duo" "this" {
  api_hostname    = var.api_hostname
  integration_key = var.integration_key
  mount_accessor  = var.mount_accessor
  name            = var.name
  push_info       = var.push_info
  secret_key      = var.secret_key
  username_format = var.username_format
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_mfa_duo.this.id
}

output "this" {
  value = vault_mfa_duo.this
}
```

[top](#index)