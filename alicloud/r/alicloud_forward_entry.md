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
    alicloud = ">= 1.111.0"
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
```

[top](#index)

### Resource

```terraform
resource "alicloud_forward_entry" "this" {
  external_ip      = var.external_ip
  external_port    = var.external_port
  forward_table_id = var.forward_table_id
  internal_ip      = var.internal_ip
  internal_port    = var.internal_port
  ip_protocol      = var.ip_protocol
  name             = var.name
}
```

[top](#index)

### Outputs

```terraform
output "forward_entry_id" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.forward_entry_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_forward_entry.this.id
}

output "this" {
  value = alicloud_forward_entry.this
}
```

[top](#index)