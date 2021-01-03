# vault_rgp_policy

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
module "vault_rgp_policy" {
  source = "./modules/vault/r/vault_rgp_policy"

  # enforcement_level - (required) is a type of string
  enforcement_level = null
  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "enforcement_level" {
  description = "(required) - Enforcement level of Sentinel policy. Can be one of: 'advisory', 'soft-mandatory' or 'hard-mandatory'"
  type        = string
}

variable "name" {
  description = "(required) - Name of the policy"
  type        = string
}

variable "policy" {
  description = "(required) - The policy document"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_rgp_policy" "this" {
  enforcement_level = var.enforcement_level
  name              = var.name
  policy            = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_rgp_policy.this.id
}

output "this" {
  value = vault_rgp_policy.this
}
```

[top](#index)