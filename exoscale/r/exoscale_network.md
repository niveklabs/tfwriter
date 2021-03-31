# exoscale_network

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_network" {
  source = "./modules/exoscale/r/exoscale_network"

  # display_text - (optional) is a type of string
  display_text = null
  # end_ip - (optional) is a type of string
  end_ip = null
  # name - (required) is a type of string
  name = null
  # netmask - (optional) is a type of string
  netmask = null
  # network_offering - (optional) is a type of string
  network_offering = null
  # start_ip - (optional) is a type of string
  start_ip = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone - (required) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_text" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_offering" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Map of tags (key: value)"
  type        = map(string)
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_network" "this" {
  display_text     = var.display_text
  end_ip           = var.end_ip
  name             = var.name
  netmask          = var.netmask
  network_offering = var.network_offering
  start_ip         = var.start_ip
  tags             = var.tags
  zone             = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_text" {
  description = "returns a string"
  value       = exoscale_network.this.display_text
}

output "id" {
  description = "returns a string"
  value       = exoscale_network.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = exoscale_network.this.tags
}

output "this" {
  value = exoscale_network.this
}
```

[top](#index)