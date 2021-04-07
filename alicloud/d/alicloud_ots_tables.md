# alicloud_ots_tables

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
module "alicloud_ots_tables" {
  source = "./modules/alicloud/d/alicloud_ots_tables"

  # ids - (optional) is a type of list of string
  ids = []
  # instance_name - (required) is a type of string
  instance_name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
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

variable "instance_name" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_ots_tables" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # instance_name - (required) is a type of string
  instance_name = var.instance_name
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ots_tables.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ots_tables.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ots_tables.this.names
}

output "tables" {
  description = "returns a list of object"
  value       = data.alicloud_ots_tables.this.tables
}

output "this" {
  value = alicloud_ots_tables.this
}
```

[top](#index)