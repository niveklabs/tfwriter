# checkpoint_management_verify_revert

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
module "checkpoint_management_verify_revert" {
  source = "./modules/checkpoint/r/checkpoint_management_verify_revert"

  # to_session - (required) is a type of string
  to_session = null
}
```

[top](#index)

### Variables

```terraform
variable "to_session" {
  description = "(required) - Session unique identifier. Specify the session you would like to verify a revert operation to."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_verify_revert" "this" {
  # to_session - (required) is a type of string
  to_session = var.to_session
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_verify_revert.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_verify_revert.this.task_id
}

output "this" {
  value = checkpoint_management_verify_revert.this
}
```

[top](#index)