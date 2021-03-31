# alicloud_snat_entries

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_snat_entries" {
  source = "./modules/alicloud/d/alicloud_snat_entries"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # snat_entry_name - (optional) is a type of string
  snat_entry_name = null
  # snat_ip - (optional) is a type of string
  snat_ip = null
  # snat_table_id - (required) is a type of string
  snat_table_id = null
  # source_cidr - (optional) is a type of string
  source_cidr = null
  # source_vswitch_id - (optional) is a type of string
  source_vswitch_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
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

variable "snat_entry_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snat_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snat_table_id" {
  description = "(required)"
  type        = string
}

variable "source_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_vswitch_id" {
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
data "alicloud_snat_entries" "this" {
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  snat_entry_name   = var.snat_entry_name
  snat_ip           = var.snat_ip
  snat_table_id     = var.snat_table_id
  source_cidr       = var.source_cidr
  source_vswitch_id = var.source_vswitch_id
  status            = var.status
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.alicloud_snat_entries.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_snat_entries.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_snat_entries.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_snat_entries.this.names
}

output "this" {
  value = alicloud_snat_entries.this
}
```

[top](#index)