# packet_volume

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_volume" {
  source = "./modules/packet/r/packet_volume"

  # billing_cycle - (optional) is a type of string
  billing_cycle = null
  # description - (optional) is a type of string
  description = null
  # facility - (required) is a type of string
  facility = null
  # locked - (optional) is a type of bool
  locked = null
  # plan - (required) is a type of string
  plan = null
  # project_id - (required) is a type of string
  project_id = null
  # size - (required) is a type of number
  size = null

  snapshot_policies = [{
    snapshot_count     = null
    snapshot_frequency = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "billing_cycle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "facility" {
  description = "(required)"
  type        = string
}

variable "locked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "plan" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "snapshot_policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      snapshot_count     = number
      snapshot_frequency = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "packet_volume" "this" {
  # billing_cycle - (optional) is a type of string
  billing_cycle = var.billing_cycle
  # description - (optional) is a type of string
  description = var.description
  # facility - (required) is a type of string
  facility = var.facility
  # locked - (optional) is a type of bool
  locked = var.locked
  # plan - (required) is a type of string
  plan = var.plan
  # project_id - (required) is a type of string
  project_id = var.project_id
  # size - (required) is a type of number
  size = var.size

  dynamic "snapshot_policies" {
    for_each = var.snapshot_policies
    content {
      # snapshot_count - (required) is a type of number
      snapshot_count = snapshot_policies.value["snapshot_count"]
      # snapshot_frequency - (required) is a type of string
      snapshot_frequency = snapshot_policies.value["snapshot_frequency"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attachments" {
  description = "returns a list of object"
  value       = packet_volume.this.attachments
}

output "billing_cycle" {
  description = "returns a string"
  value       = packet_volume.this.billing_cycle
}

output "created" {
  description = "returns a string"
  value       = packet_volume.this.created
}

output "id" {
  description = "returns a string"
  value       = packet_volume.this.id
}

output "name" {
  description = "returns a string"
  value       = packet_volume.this.name
}

output "state" {
  description = "returns a string"
  value       = packet_volume.this.state
}

output "updated" {
  description = "returns a string"
  value       = packet_volume.this.updated
}

output "this" {
  value = packet_volume.this
}
```

[top](#index)