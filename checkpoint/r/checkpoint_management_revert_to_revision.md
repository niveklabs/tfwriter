# checkpoint_management_revert_to_revision

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_revert_to_revision" {
  source = "./modules/checkpoint/r/checkpoint_management_revert_to_revision"

  # to_session - (optional) is a type of string
  to_session = null
}
```

[top](#index)

### Variables

```terraform
variable "to_session" {
  description = "(optional) - Session unique identifier. Specify the session  id you would like to revert your database to."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_revert_to_revision" "this" {
  to_session = var.to_session
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_revert_to_revision.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_revert_to_revision.this.task_id
}

output "this" {
  value = checkpoint_management_revert_to_revision.this
}
```

[top](#index)