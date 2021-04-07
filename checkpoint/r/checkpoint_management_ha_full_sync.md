# checkpoint_management_ha_full_sync

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
module "checkpoint_management_ha_full_sync" {
  source = "./modules/checkpoint/r/checkpoint_management_ha_full_sync"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Peer name (Multi Domain Server, Domain Server or Security Management Server)."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Peer unique identifier (Multi Domain Server, Domain Server or Security Management Server)."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_ha_full_sync" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_ha_full_sync.this.id
}

output "task_id" {
  description = "returns a string"
  value       = checkpoint_management_ha_full_sync.this.task_id
}

output "this" {
  value = checkpoint_management_ha_full_sync.this
}
```

[top](#index)