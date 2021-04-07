# exoscale_nic

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
module "exoscale_nic" {
  source = "./modules/exoscale/r/exoscale_nic"

  # compute_id - (required) is a type of string
  compute_id = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # network_id - (required) is a type of string
  network_id = null

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
variable "compute_id" {
  description = "(required)"
  type        = string
}

variable "ip_address" {
  description = "(optional) - IP address"
  type        = string
  default     = null
}

variable "network_id" {
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
resource "exoscale_nic" "this" {
  # compute_id - (required) is a type of string
  compute_id = var.compute_id
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # network_id - (required) is a type of string
  network_id = var.network_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "gateway" {
  description = "returns a string"
  value       = exoscale_nic.this.gateway
}

output "id" {
  description = "returns a string"
  value       = exoscale_nic.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = exoscale_nic.this.ip_address
}

output "mac_address" {
  description = "returns a string"
  value       = exoscale_nic.this.mac_address
}

output "netmask" {
  description = "returns a string"
  value       = exoscale_nic.this.netmask
}

output "this" {
  value = exoscale_nic.this
}
```

[top](#index)