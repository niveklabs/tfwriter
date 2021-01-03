# alicloud_snat_entry

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
module "alicloud_snat_entry" {
  source = "./modules/alicloud/r/alicloud_snat_entry"

  # snat_entry_name - (optional) is a type of string
  snat_entry_name = null
  # snat_ip - (required) is a type of string
  snat_ip = null
  # snat_table_id - (required) is a type of string
  snat_table_id = null
  # source_cidr - (optional) is a type of string
  source_cidr = null
  # source_vswitch_id - (optional) is a type of string
  source_vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "snat_entry_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snat_ip" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "alicloud_snat_entry" "this" {
  snat_entry_name   = var.snat_entry_name
  snat_ip           = var.snat_ip
  snat_table_id     = var.snat_table_id
  source_cidr       = var.source_cidr
  source_vswitch_id = var.source_vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_snat_entry.this.id
}

output "snat_entry_id" {
  description = "returns a string"
  value       = alicloud_snat_entry.this.snat_entry_id
}

output "this" {
  value = alicloud_snat_entry.this
}
```

[top](#index)