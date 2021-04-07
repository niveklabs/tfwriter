# alicloud_sag_qos_policy

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
module "alicloud_sag_qos_policy" {
  source = "./modules/alicloud/r/alicloud_sag_qos_policy"

  # description - (optional) is a type of string
  description = null
  # dest_cidr - (required) is a type of string
  dest_cidr = null
  # dest_port_range - (required) is a type of string
  dest_port_range = null
  # end_time - (optional) is a type of string
  end_time = null
  # ip_protocol - (required) is a type of string
  ip_protocol = null
  # name - (optional) is a type of string
  name = null
  # priority - (required) is a type of number
  priority = null
  # qos_id - (required) is a type of string
  qos_id = null
  # source_cidr - (required) is a type of string
  source_cidr = null
  # source_port_range - (required) is a type of string
  source_port_range = null
  # start_time - (optional) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dest_cidr" {
  description = "(required)"
  type        = string
}

variable "dest_port_range" {
  description = "(required)"
  type        = string
}

variable "end_time" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "priority" {
  description = "(required)"
  type        = number
}

variable "qos_id" {
  description = "(required)"
  type        = string
}

variable "source_cidr" {
  description = "(required)"
  type        = string
}

variable "source_port_range" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_sag_qos_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dest_cidr - (required) is a type of string
  dest_cidr = var.dest_cidr
  # dest_port_range - (required) is a type of string
  dest_port_range = var.dest_port_range
  # end_time - (optional) is a type of string
  end_time = var.end_time
  # ip_protocol - (required) is a type of string
  ip_protocol = var.ip_protocol
  # name - (optional) is a type of string
  name = var.name
  # priority - (required) is a type of number
  priority = var.priority
  # qos_id - (required) is a type of string
  qos_id = var.qos_id
  # source_cidr - (required) is a type of string
  source_cidr = var.source_cidr
  # source_port_range - (required) is a type of string
  source_port_range = var.source_port_range
  # start_time - (optional) is a type of string
  start_time = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_sag_qos_policy.this.id
}

output "this" {
  value = alicloud_sag_qos_policy.this
}
```

[top](#index)