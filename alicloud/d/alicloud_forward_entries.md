# alicloud_forward_entries

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_forward_entries" {
  source = "./modules/alicloud/d/alicloud_forward_entries"

  # external_ip - (optional) is a type of string
  external_ip = null
  # external_port - (optional) is a type of string
  external_port = null
  # forward_entry_name - (optional) is a type of string
  forward_entry_name = null
  # forward_table_id - (required) is a type of string
  forward_table_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # internal_ip - (optional) is a type of string
  internal_ip = null
  # internal_port - (optional) is a type of string
  internal_port = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "external_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_port" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "internal_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internal_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_forward_entries" "this" {
  # external_ip - (optional) is a type of string
  external_ip = var.external_ip
  # external_port - (optional) is a type of string
  external_port = var.external_port
  # forward_entry_name - (optional) is a type of string
  forward_entry_name = var.forward_entry_name
  # forward_table_id - (required) is a type of string
  forward_table_id = var.forward_table_id
  # ids - (optional) is a type of list of string
  ids = var.ids
  # internal_ip - (optional) is a type of string
  internal_ip = var.internal_ip
  # internal_port - (optional) is a type of string
  internal_port = var.internal_port
  # ip_protocol - (optional) is a type of string
  ip_protocol = var.ip_protocol
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.alicloud_forward_entries.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_forward_entries.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_forward_entries.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_forward_entries.this.names
}

output "this" {
  value = alicloud_forward_entries.this
}
```

[top](#index)