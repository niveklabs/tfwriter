# checkpoint_management_set_ha_state

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
module "checkpoint_management_set_ha_state" {
  source = "./modules/checkpoint/r/checkpoint_management_set_ha_state"

  # new_state - (required) is a type of string
  new_state = null
}
```

[top](#index)

### Variables

```terraform
variable "new_state" {
  description = "(required) - Domain server new state."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_set_ha_state" "this" {
  # new_state - (required) is a type of string
  new_state = var.new_state
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_set_ha_state.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_set_ha_state.this.task_id
}

output "this" {
  value = checkpoint_management_set_ha_state.this
}
```

[top](#index)