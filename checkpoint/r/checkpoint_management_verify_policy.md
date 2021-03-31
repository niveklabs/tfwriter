# checkpoint_management_verify_policy

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_verify_policy" {
  source = "./modules/checkpoint/r/checkpoint_management_verify_policy"

  # policy_package - (required) is a type of string
  policy_package = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_package" {
  description = "(required) - Policy package identified by the name or UID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_verify_policy" "this" {
  policy_package = var.policy_package
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_verify_policy.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_verify_policy.this.task_id
}

output "this" {
  value = checkpoint_management_verify_policy.this
}
```

[top](#index)