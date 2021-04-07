# vault_identity_entity

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
module "vault_identity_entity" {
  source = "./modules/vault/d/vault_identity_entity"

  # alias_id - (optional) is a type of string
  alias_id = null
  # alias_mount_accessor - (optional) is a type of string
  alias_mount_accessor = null
  # alias_name - (optional) is a type of string
  alias_name = null
  # entity_id - (optional) is a type of string
  entity_id = null
  # entity_name - (optional) is a type of string
  entity_name = null
}
```

[top](#index)

### Variables

```terraform
variable "alias_id" {
  description = "(optional) - ID of the alias."
  type        = string
  default     = null
}

variable "alias_mount_accessor" {
  description = "(optional) - Accessor of the mount to which the alias belongs to. This should be supplied in conjunction with `alias_name`."
  type        = string
  default     = null
}

variable "alias_name" {
  description = "(optional) - Name of the alias. This should be supplied in conjunction with `alias_mount_accessor`."
  type        = string
  default     = null
}

variable "entity_id" {
  description = "(optional) - ID of the entity."
  type        = string
  default     = null
}

variable "entity_name" {
  description = "(optional) - Name of the entity."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vault_identity_entity" "this" {
  # alias_id - (optional) is a type of string
  alias_id = var.alias_id
  # alias_mount_accessor - (optional) is a type of string
  alias_mount_accessor = var.alias_mount_accessor
  # alias_name - (optional) is a type of string
  alias_name = var.alias_name
  # entity_id - (optional) is a type of string
  entity_id = var.entity_id
  # entity_name - (optional) is a type of string
  entity_name = var.entity_name
}
```

[top](#index)

### Outputs

```terraform
output "alias_id" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.alias_id
}

output "alias_mount_accessor" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.alias_mount_accessor
}

output "alias_name" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.alias_name
}

output "aliases" {
  description = "returns a set of object"
  value       = data.vault_identity_entity.this.aliases
}

output "creation_time" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.creation_time
}

output "data_json" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.data_json
}

output "direct_group_ids" {
  description = "returns a set of string"
  value       = data.vault_identity_entity.this.direct_group_ids
}

output "disabled" {
  description = "returns a bool"
  value       = data.vault_identity_entity.this.disabled
}

output "entity_id" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.entity_id
}

output "entity_name" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.entity_name
}

output "group_ids" {
  description = "returns a set of string"
  value       = data.vault_identity_entity.this.group_ids
}

output "id" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.id
}

output "inherited_group_ids" {
  description = "returns a set of string"
  value       = data.vault_identity_entity.this.inherited_group_ids
}

output "last_update_time" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.last_update_time
}

output "merged_entity_ids" {
  description = "returns a set of string"
  value       = data.vault_identity_entity.this.merged_entity_ids
}

output "metadata" {
  description = "returns a map of string"
  value       = data.vault_identity_entity.this.metadata
}

output "namespace_id" {
  description = "returns a string"
  value       = data.vault_identity_entity.this.namespace_id
}

output "policies" {
  description = "returns a set of string"
  value       = data.vault_identity_entity.this.policies
}

output "this" {
  value = vault_identity_entity.this
}
```

[top](#index)