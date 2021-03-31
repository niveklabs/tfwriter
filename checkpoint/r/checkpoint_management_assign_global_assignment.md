# checkpoint_management_assign_global_assignment

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
module "checkpoint_management_assign_global_assignment" {
  source = "./modules/checkpoint/r/checkpoint_management_assign_global_assignment"

  # dependent_domains - (optional) is a type of set of string
  dependent_domains = []
  # global_domains - (optional) is a type of set of string
  global_domains = []
}
```

[top](#index)

### Variables

```terraform
variable "dependent_domains" {
  description = "(optional) - N/A"
  type        = set(string)
  default     = null
}

variable "global_domains" {
  description = "(optional) - N/A"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_assign_global_assignment" "this" {
  dependent_domains = var.dependent_domains
  global_domains    = var.global_domains
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_assign_global_assignment.this.id
}

output "tasks" {
  description = "returns a set of string"
  value       = checkpoint_management_assign_global_assignment.this.tasks
}

output "this" {
  value = checkpoint_management_assign_global_assignment.this
}
```

[top](#index)