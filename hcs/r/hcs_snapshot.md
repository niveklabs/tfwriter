# hcs_snapshot

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcs = ">= 0.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcs_snapshot" {
  source = "./modules/hcs/r/hcs_snapshot"

  # managed_application_name - (required) is a type of string
  managed_application_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # snapshot_name - (required) is a type of string
  snapshot_name = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "managed_application_name" {
  description = "(required) - The name of the HCS Azure Managed Application."
  type        = string
}

variable "resource_group_name" {
  description = "(required) - The name of the Resource Group in which the HCS Azure Managed Application belongs."
  type        = string
}

variable "snapshot_name" {
  description = "(required) - The name of the snapshot."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcs_snapshot" "this" {
  managed_application_name = var.managed_application_name
  resource_group_name      = var.resource_group_name
  snapshot_name            = var.snapshot_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "finished_at" {
  description = "returns a string"
  value       = hcs_snapshot.this.finished_at
}

output "id" {
  description = "returns a string"
  value       = hcs_snapshot.this.id
}

output "requested_at" {
  description = "returns a string"
  value       = hcs_snapshot.this.requested_at
}

output "restored_at" {
  description = "returns a string"
  value       = hcs_snapshot.this.restored_at
}

output "size" {
  description = "returns a number"
  value       = hcs_snapshot.this.size
}

output "state" {
  description = "returns a string"
  value       = hcs_snapshot.this.state
}

output "this" {
  value = hcs_snapshot.this
}
```

[top](#index)