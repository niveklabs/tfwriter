# vault_identity_group_member_entity_ids

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
module "vault_identity_group_member_entity_ids" {
  source = "./modules/vault/r/vault_identity_group_member_entity_ids"

  # exclusive - (optional) is a type of bool
  exclusive = null
  # group_id - (required) is a type of string
  group_id = null
  # member_entity_ids - (optional) is a type of set of string
  member_entity_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "exclusive" {
  description = "(optional) - Should the resource manage member entity ids exclusively? Beware of race conditions when disabling exclusive management"
  type        = bool
  default     = null
}

variable "group_id" {
  description = "(required) - ID of the group."
  type        = string
}

variable "member_entity_ids" {
  description = "(optional) - Entity IDs to be assigned as group members."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_group_member_entity_ids" "this" {
  # exclusive - (optional) is a type of bool
  exclusive = var.exclusive
  # group_id - (required) is a type of string
  group_id = var.group_id
  # member_entity_ids - (optional) is a type of set of string
  member_entity_ids = var.member_entity_ids
}
```

[top](#index)

### Outputs

```terraform
output "group_name" {
  description = "returns a string"
  value       = vault_identity_group_member_entity_ids.this.group_name
}

output "id" {
  description = "returns a string"
  value       = vault_identity_group_member_entity_ids.this.id
}

output "this" {
  value = vault_identity_group_member_entity_ids.this
}
```

[top](#index)