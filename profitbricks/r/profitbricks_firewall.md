# profitbricks_firewall

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
module "profitbricks_firewall" {
  source = "./modules/profitbricks/r/profitbricks_firewall"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # icmp_code - (optional) is a type of string
  icmp_code = null
  # icmp_type - (optional) is a type of string
  icmp_type = null
  # name - (optional) is a type of string
  name = null
  # nic_id - (required) is a type of string
  nic_id = null
  # port_range_end - (optional) is a type of number
  port_range_end = null
  # port_range_start - (optional) is a type of number
  port_range_start = null
  # protocol - (required) is a type of string
  protocol = null
  # server_id - (required) is a type of string
  server_id = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_mac - (optional) is a type of string
  source_mac = null
  # target_ip - (optional) is a type of string
  target_ip = null

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

variable "icmp_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmp_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nic_id" {
  description = "(required)"
  type        = string
}

variable "port_range_end" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_range_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_ip" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "profitbricks_firewall" "this" {
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
  # icmp_code - (optional) is a type of string
  icmp_code = var.icmp_code
  # icmp_type - (optional) is a type of string
  icmp_type = var.icmp_type
  # name - (optional) is a type of string
  name = var.name
  # nic_id - (required) is a type of string
  nic_id = var.nic_id
  # port_range_end - (optional) is a type of number
  port_range_end = var.port_range_end
  # port_range_start - (optional) is a type of number
  port_range_start = var.port_range_start
  # protocol - (required) is a type of string
  protocol = var.protocol
  # server_id - (required) is a type of string
  server_id = var.server_id
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # source_mac - (optional) is a type of string
  source_mac = var.source_mac
  # target_ip - (optional) is a type of string
  target_ip = var.target_ip

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
  value       = profitbricks_firewall.this.id
}

output "this" {
  value = profitbricks_firewall.this
}
```

[top](#index)