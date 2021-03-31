# vault_egp_policy

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
module "vault_egp_policy" {
  source = "./modules/vault/r/vault_egp_policy"

  # enforcement_level - (required) is a type of string
  enforcement_level = null
  # name - (required) is a type of string
  name = null
  # paths - (required) is a type of list of string
  paths = []
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

variable "paths" {
  description = "(required) - List of paths to which the policy will be applied"
  type        = list(string)
}

variable "policy" {
  description = "(required) - The policy document"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_egp_policy" "this" {
  enforcement_level = var.enforcement_level
  name              = var.name
  paths             = var.paths
  policy            = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_egp_policy.this.id
}

output "this" {
  value = vault_egp_policy.this
}
```

[top](#index)