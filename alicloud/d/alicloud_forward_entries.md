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
    alicloud = ">= 1.111.0"
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
  # forward_table_id - (required) is a type of string
  forward_table_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # internal_ip - (optional) is a type of string
  internal_ip = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # names - (optional) is a type of list of string
  names = []
  # output_file - (optional) is a type of string
  output_file = null
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

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_forward_entries" "this" {
  external_ip      = var.external_ip
  forward_table_id = var.forward_table_id
  ids              = var.ids
  internal_ip      = var.internal_ip
  name_regex       = var.name_regex
  names            = var.names
  output_file      = var.output_file
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

output "this" {
  value = alicloud_forward_entries.this
}
```

[top](#index)