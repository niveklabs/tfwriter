# vault_identity_group_policies

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_identity_group_policies" {
  source = "./modules/vault/r/vault_identity_group_policies"

  # exclusive - (optional) is a type of bool
  exclusive = null
  # group_id - (required) is a type of string
  group_id = null
  # policies - (required) is a type of set of string
  policies = []
}
```

[top](#index)

### Variables

```terraform
variable "exclusive" {
  description = "(optional) - Should the resource manage policies exclusively? Beware of race conditions when disabling exclusive management"
  type        = bool
  default     = null
}

variable "group_id" {
  description = "(required) - ID of the group."
  type        = string
}

variable "policies" {
  description = "(required) - Policies to be tied to the group."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_group_policies" "this" {
  exclusive = var.exclusive
  group_id  = var.group_id
  policies  = var.policies
}
```

[top](#index)

### Outputs

```terraform
output "group_name" {
  description = "returns a string"
  value       = vault_identity_group_policies.this.group_name
}

output "id" {
  description = "returns a string"
  value       = vault_identity_group_policies.this.id
}

output "this" {
  value = vault_identity_group_policies.this
}
```

[top](#index)