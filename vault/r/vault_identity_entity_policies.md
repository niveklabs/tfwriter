# vault_identity_entity_policies

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
module "vault_identity_entity_policies" {
  source = "./modules/vault/r/vault_identity_entity_policies"

  # entity_id - (required) is a type of string
  entity_id = null
  # exclusive - (optional) is a type of bool
  exclusive = null
  # policies - (required) is a type of set of string
  policies = []
}
```

[top](#index)

### Variables

```terraform
variable "entity_id" {
  description = "(required) - ID of the entity."
  type        = string
}

variable "exclusive" {
  description = "(optional) - Should the resource manage policies exclusively"
  type        = bool
  default     = null
}

variable "policies" {
  description = "(required) - Policies to be tied to the entity."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_entity_policies" "this" {
  # entity_id - (required) is a type of string
  entity_id = var.entity_id
  # exclusive - (optional) is a type of bool
  exclusive = var.exclusive
  # policies - (required) is a type of set of string
  policies = var.policies
}
```

[top](#index)

### Outputs

```terraform
output "entity_name" {
  description = "returns a string"
  value       = vault_identity_entity_policies.this.entity_name
}

output "id" {
  description = "returns a string"
  value       = vault_identity_entity_policies.this.id
}

output "this" {
  value = vault_identity_entity_policies.this
}
```

[top](#index)