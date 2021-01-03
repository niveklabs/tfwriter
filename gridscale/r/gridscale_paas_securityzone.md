# gridscale_paas_securityzone

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
module "gridscale_paas_securityzone" {
  source = "./modules/gridscale/r/gridscale_paas_securityzone"

  # labels - (optional) is a type of set of string
  labels = []
  # location_uuid - (optional) is a type of string
  location_uuid = null
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
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "location_uuid" {
  description = "(optional) - Helps to identify which datacenter an object belongs to"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object"
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
resource "gridscale_paas_securityzone" "this" {
  labels        = var.labels
  location_uuid = var.location_uuid
  name          = var.name

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
  value       = gridscale_paas_securityzone.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.create_time
}

output "id" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.id
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.location_uuid
}

output "relations" {
  description = "returns a set of string"
  value       = gridscale_paas_securityzone.this.relations
}

output "status" {
  description = "returns a string"
  value       = gridscale_paas_securityzone.this.status
}

output "this" {
  value = gridscale_paas_securityzone.this
}
```

[top](#index)