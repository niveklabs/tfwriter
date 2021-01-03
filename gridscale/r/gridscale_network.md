# gridscale_network

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_network" {
  source = "./modules/gridscale/r/gridscale_network"

  # l2security - (optional) is a type of bool
  l2security = null
  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "l2security" {
  description = "(optional) - MAC spoofing protection - filters layer2 and ARP traffic based on source MAC"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "gridscale_network" "this" {
  l2security = var.l2security
  labels     = var.labels
  name       = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = gridscale_network.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_network.this.create_time
}

output "delete_block" {
  description = "returns a bool"
  value       = gridscale_network.this.delete_block
}

output "id" {
  description = "returns a string"
  value       = gridscale_network.this.id
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_network.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_network.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_network.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_network.this.location_uuid
}

output "network_type" {
  description = "returns a string"
  value       = gridscale_network.this.network_type
}

output "status" {
  description = "returns a string"
  value       = gridscale_network.this.status
}

output "this" {
  value = gridscale_network.this
}
```

[top](#index)