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
    alicloud = ">= 1.111.0"
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
  # output_file - (optional) is a type of string
  output_file = null
  # snat_ip - (optional) is a type of string
  snat_ip = null
  # snat_table_id - (required) is a type of string
  snat_table_id = null
  # source_cidr - (optional) is a type of string
  source_cidr = null
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

variable "output_file" {
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_snat_entries" "this" {
  ids           = var.ids
  output_file   = var.output_file
  snat_ip       = var.snat_ip
  snat_table_id = var.snat_table_id
  source_cidr   = var.source_cidr
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

output "this" {
  value = alicloud_snat_entries.this
}
```

[top](#index)