# alicloud_forward_entry

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_forward_entry" {
  source = "./modules/alicloud/r/alicloud_forward_entry"

  # external_ip - (required) is a type of string
  external_ip = null
  # external_port - (required) is a type of string
  external_port = null
  # forward_entry_name - (optional) is a type of string
  forward_entry_name = null
  # forward_table_id - (required) is a type of string
  forward_table_id = null
  # internal_ip - (required) is a type of string
  internal_ip = null
  # internal_port - (required) is a type of string
  internal_port = null
  # ip_protocol - (required) is a type of string
  ip_protocol = null
  # name - (optional) is a type of string
  name = null
  # port_break - (optional) is a type of bool
  port_break = null

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
variable "external_ip" {
  description = "(required)"
  type        = string
}

variable "external_port" {
  description = "(required)"
  type        = string
}

variable "forward_entry_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_table_id" {
  description = "(required)"
  type        = string
}

variable "internal_ip" {
  description = "(required)"
  type        = string
}

variable "internal_port" {
  description = "(required)"
  type        = string
}

variable "ip_protocol" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_break" {
  description = "(optional)"
  type        = bool
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
resource "alicloud_forward_entry" "this" {
  # external_ip - (required) is a type of string
  external_ip = var.external_ip
  # external_port - (required) is a type of string
  external_port = var.external_port
  # forward_entry_name - (optional) is a type of string
  forward_entry_name = var.forward_entry_name
  # forward_table_id - (required) is a type of string
  forward_table_id = var.forward_table_id
  # internal_ip - (required) is a type of string
  internal_ip = var.internal_ip
  # internal_port - (required) is a type of string
  internal_port = var.internal_port
  # ip_protocol - (required) is a type of string
  ip_protocol = var.ip_protocol
  # name - (optional) is a type of string
  name = var.name
  # port_break - (optional) is a type of bool
  port_break = var.port_break

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
output "forward_entry_id" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.forward_entry_id
}

output "forward_entry_name" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.forward_entry_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.name
}

output "status" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.status
}

output "this" {
  value = alicloud_forward_entry.this
}
```

[top](#index)