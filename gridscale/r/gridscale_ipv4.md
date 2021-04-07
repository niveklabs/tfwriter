# gridscale_ipv4

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
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_ipv4" {
  source = "./modules/gridscale/r/gridscale_ipv4"

  # failover - (optional) is a type of bool
  failover = null
  # labels - (optional) is a type of set of string
  labels = []
  # name - (optional) is a type of string
  name = null
  # reverse_dns - (optional) is a type of string
  reverse_dns = null

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
variable "failover" {
  description = "(optional) - Sets failover mode for this IP. If true, then this IP is no longer available for DHCP and can no longer be related to any server."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters."
  type        = string
  default     = null
}

variable "reverse_dns" {
  description = "(optional) - Defines the reverse DNS entry for the IP address (PTR Resource Record)."
  type        = string
  default     = null
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
resource "gridscale_ipv4" "this" {
  # failover - (optional) is a type of bool
  failover = var.failover
  # labels - (optional) is a type of set of string
  labels = var.labels
  # name - (optional) is a type of string
  name = var.name
  # reverse_dns - (optional) is a type of string
  reverse_dns = var.reverse_dns

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = gridscale_ipv4.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_ipv4.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_ipv4.this.current_price
}

output "delete_block" {
  description = "returns a bool"
  value       = gridscale_ipv4.this.delete_block
}

output "id" {
  description = "returns a string"
  value       = gridscale_ipv4.this.id
}

output "ip" {
  description = "returns a string"
  value       = gridscale_ipv4.this.ip
}

output "location_country" {
  description = "returns a string"
  value       = gridscale_ipv4.this.location_country
}

output "location_iata" {
  description = "returns a string"
  value       = gridscale_ipv4.this.location_iata
}

output "location_name" {
  description = "returns a string"
  value       = gridscale_ipv4.this.location_name
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_ipv4.this.location_uuid
}

output "prefix" {
  description = "returns a string"
  value       = gridscale_ipv4.this.prefix
}

output "reverse_dns" {
  description = "returns a string"
  value       = gridscale_ipv4.this.reverse_dns
}

output "status" {
  description = "returns a string"
  value       = gridscale_ipv4.this.status
}

output "usage_in_minutes" {
  description = "returns a number"
  value       = gridscale_ipv4.this.usage_in_minutes
}

output "this" {
  value = gridscale_ipv4.this
}
```

[top](#index)