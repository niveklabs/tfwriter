# profitbricks_loadbalancer

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_loadbalancer" {
  source = "./modules/profitbricks/r/profitbricks_loadbalancer"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # dhcp - (optional) is a type of bool
  dhcp = null
  # ip - (optional) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # nic_ids - (required) is a type of list of string
  nic_ids = []

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
variable "datacenter_id" {
  description = "(required)"
  type        = string
}

variable "dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nic_ids" {
  description = "(required)"
  type        = list(string)
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
resource "profitbricks_loadbalancer" "this" {
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
  # dhcp - (optional) is a type of bool
  dhcp = var.dhcp
  # ip - (optional) is a type of string
  ip = var.ip
  # name - (required) is a type of string
  name = var.name
  # nic_ids - (required) is a type of list of string
  nic_ids = var.nic_ids

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
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
output "id" {
  description = "returns a string"
  value       = profitbricks_loadbalancer.this.id
}

output "this" {
  value = profitbricks_loadbalancer.this
}
```

[top](#index)