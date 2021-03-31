# vault_identity_group

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
module "vault_identity_group" {
  source = "./modules/vault/r/vault_identity_group"

  # external_member_entity_ids - (optional) is a type of bool
  external_member_entity_ids = null
  # external_policies - (optional) is a type of bool
  external_policies = null
  # member_entity_ids - (optional) is a type of set of string
  member_entity_ids = []
  # member_group_ids - (optional) is a type of set of string
  member_group_ids = []
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (optional) is a type of string
  name = null
  # policies - (optional) is a type of set of string
  policies = []
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "external_member_entity_ids" {
  description = "(optional) - Manage member entities externally through `vault_identity_group_policies_member_entity_ids`"
  type        = bool
  default     = null
}

variable "external_policies" {
  description = "(optional) - Manage policies externally through `vault_identity_group_policies`, allows using group ID in assigned policies."
  type        = bool
  default     = null
}

variable "member_entity_ids" {
  description = "(optional) - Entity IDs to be assigned as group members."
  type        = set(string)
  default     = null
}

variable "member_group_ids" {
  description = "(optional) - Group IDs to be assigned as group members."
  type        = set(string)
  default     = null
}

variable "metadata" {
  description = "(optional) - Metadata to be associated with the group."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - Name of the group."
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - Policies to be tied to the group."
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(optional) - Type of the group, internal or external. Defaults to internal."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_group" "this" {
  external_member_entity_ids = var.external_member_entity_ids
  external_policies          = var.external_policies
  member_entity_ids          = var.member_entity_ids
  member_group_ids           = var.member_group_ids
  metadata                   = var.metadata
  name                       = var.name
  policies                   = var.policies
  type                       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_identity_group.this.id
}

output "name" {
  description = "returns a string"
  value       = vault_identity_group.this.name
}

output "this" {
  value = vault_identity_group.this
}
```

[top](#index)