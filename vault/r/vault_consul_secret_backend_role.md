# vault_consul_secret_backend_role

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
module "vault_consul_secret_backend_role" {
  source = "./modules/vault/r/vault_consul_secret_backend_role"

  # backend - (optional) is a type of string
  backend = null
  # local - (optional) is a type of bool
  local = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # policies - (required) is a type of list of string
  policies = []
  # token_type - (optional) is a type of string
  token_type = null
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - The path of the Consul Secret Backend the role belongs to."
  type        = string
  default     = null
}

variable "local" {
  description = "(optional) - Indicates that the token should not be replicated globally and instead be local to the current datacenter."
  type        = bool
  default     = null
}

variable "max_ttl" {
  description = "(optional) - Maximum TTL for leases associated with this role, in seconds."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of an existing role against which to create this Consul credential"
  type        = string
}

variable "path" {
  description = "(optional) - The path of the Consul Secret Backend the role belongs to."
  type        = string
  default     = null
}

variable "policies" {
  description = "(required) - List of Consul policies to associate with this role"
  type        = list(string)
}

variable "token_type" {
  description = "(optional) - Specifies the type of token to create when using this role. Valid values are \"client\" or \"management\"."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - Specifies the TTL for this role."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_consul_secret_backend_role" "this" {
  backend    = var.backend
  local      = var.local
  max_ttl    = var.max_ttl
  name       = var.name
  path       = var.path
  policies   = var.policies
  token_type = var.token_type
  ttl        = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_consul_secret_backend_role.this.id
}

output "this" {
  value = vault_consul_secret_backend_role.this
}
```

[top](#index)