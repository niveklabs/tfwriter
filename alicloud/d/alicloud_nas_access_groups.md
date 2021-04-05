# alicloud_nas_access_groups

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
module "alicloud_nas_access_groups" {
  source = "./modules/alicloud/d/alicloud_nas_access_groups"

  # access_group_name - (optional) is a type of string
  access_group_name = null
  # access_group_type - (optional) is a type of string
  access_group_type = null
  # description - (optional) is a type of string
  description = null
  # file_system_type - (optional) is a type of string
  file_system_type = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # type - (optional) is a type of string
  type = null
  # useutc_date_time - (optional) is a type of bool
  useutc_date_time = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_system_type" {
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "useutc_date_time" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_nas_access_groups" "this" {
  access_group_name = var.access_group_name
  access_group_type = var.access_group_type
  description       = var.description
  file_system_type  = var.file_system_type
  name_regex        = var.name_regex
  output_file       = var.output_file
  type              = var.type
  useutc_date_time  = var.useutc_date_time
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.alicloud_nas_access_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_nas_access_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_nas_access_groups.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_nas_access_groups.this.names
}

output "this" {
  value = alicloud_nas_access_groups.this
}
```

[top](#index)