# vault_nomad_secret_role

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
module "vault_nomad_secret_role" {
  source = "./modules/vault/r/vault_nomad_secret_role"

  # backend - (required) is a type of string
  backend = null
  # global - (optional) is a type of bool
  global = null
  # policies - (optional) is a type of list of string
  policies = []
  # role - (required) is a type of string
  role = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The mount path for the Nomad backend."
  type        = string
}

variable "global" {
  description = "(optional) - Specifies if the token should be global."
  type        = bool
  default     = null
}

variable "policies" {
  description = "(optional) - Comma separated list of Nomad policies the token is going to be created against. These need to be created beforehand in Nomad."
  type        = list(string)
  default     = null
}

variable "role" {
  description = "(required) - Name of the role."
  type        = string
}

variable "type" {
  description = "(optional) - Specifies the type of token to create when using this role. Valid values are \"client\" or \"management\"."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_nomad_secret_role" "this" {
  backend  = var.backend
  global   = var.global
  policies = var.policies
  role     = var.role
  type     = var.type
}
```

[top](#index)

### Outputs

```terraform
output "global" {
  description = "returns a bool"
  value       = vault_nomad_secret_role.this.global
}

output "id" {
  description = "returns a string"
  value       = vault_nomad_secret_role.this.id
}

output "policies" {
  description = "returns a list of string"
  value       = vault_nomad_secret_role.this.policies
}

output "type" {
  description = "returns a string"
  value       = vault_nomad_secret_role.this.type
}

output "this" {
  value = vault_nomad_secret_role.this
}
```

[top](#index)