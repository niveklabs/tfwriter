# vault_gcp_secret_backend

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
module "vault_gcp_secret_backend" {
  source = "./modules/vault/r/vault_gcp_secret_backend"

  # credentials - (optional) is a type of string
  credentials = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # path - (optional) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "credentials" {
  description = "(optional) - JSON-encoded credentials to use to connect to GCP"
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

variable "local" {
  description = "(optional) - Local mount flag that can be explicitly set to true to enforce local mount in HA environment"
  type        = bool
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
```

[top](#index)

### Resource

```terraform
resource "vault_gcp_secret_backend" "this" {
  credentials               = var.credentials
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  description               = var.description
  local                     = var.local
  max_lease_ttl_seconds     = var.max_lease_ttl_seconds
  path                      = var.path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_gcp_secret_backend.this.id
}

output "this" {
  value = vault_gcp_secret_backend.this
}
```

[top](#index)