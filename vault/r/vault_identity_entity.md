# vault_identity_entity

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
module "vault_identity_entity" {
  source = "./modules/vault/r/vault_identity_entity"

  # disabled - (optional) is a type of bool
  disabled = null
  # external_policies - (optional) is a type of bool
  external_policies = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (optional) is a type of string
  name = null
  # policies - (optional) is a type of set of string
  policies = []
}
```

[top](#index)

### Variables

```terraform
variable "disabled" {
  description = "(optional) - Whether the entity is disabled. Disabled entities' associated tokens cannot be used, but are not revoked."
  type        = bool
  default     = null
}

variable "external_policies" {
  description = "(optional) - Manage policies externally through `vault_identity_entity_policies`."
  type        = bool
  default     = null
}

variable "metadata" {
  description = "(optional) - Metadata to be associated with the entity."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - Name of the entity."
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - Policies to be tied to the entity."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_entity" "this" {
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # external_policies - (optional) is a type of bool
  external_policies = var.external_policies
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (optional) is a type of string
  name = var.name
  # policies - (optional) is a type of set of string
  policies = var.policies
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_identity_entity.this.id
}

output "name" {
  description = "returns a string"
  value       = vault_identity_entity.this.name
}

output "this" {
  value = vault_identity_entity.this
}
```

[top](#index)