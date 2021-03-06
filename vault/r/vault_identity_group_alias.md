# vault_identity_group_alias

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
module "vault_identity_group_alias" {
  source = "./modules/vault/r/vault_identity_group_alias"

  # canonical_id - (required) is a type of string
  canonical_id = null
  # mount_accessor - (required) is a type of string
  mount_accessor = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "canonical_id" {
  description = "(required) - ID of the group to which this is an alias."
  type        = string
}

variable "mount_accessor" {
  description = "(required) - Mount accessor to which this alias belongs to."
  type        = string
}

variable "name" {
  description = "(required) - Name of the group alias."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_group_alias" "this" {
  # canonical_id - (required) is a type of string
  canonical_id = var.canonical_id
  # mount_accessor - (required) is a type of string
  mount_accessor = var.mount_accessor
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_identity_group_alias.this.id
}

output "this" {
  value = vault_identity_group_alias.this
}
```

[top](#index)