# vault_policy

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
module "vault_policy" {
  source = "./modules/vault/r/vault_policy"

  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
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
resource "vault_policy" "this" {
  name   = var.name
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_policy.this.id
}

output "this" {
  value = vault_policy.this
}
```

[top](#index)