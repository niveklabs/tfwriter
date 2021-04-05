# alicloud_resource_manager_folders

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
module "alicloud_resource_manager_folders" {
  source = "./modules/alicloud/d/alicloud_resource_manager_folders"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # parent_folder_id - (optional) is a type of string
  parent_folder_id = null
  # query_keyword - (optional) is a type of string
  query_keyword = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "parent_folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_keyword" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_folders" "this" {
  enable_details   = var.enable_details
  ids              = var.ids
  name_regex       = var.name_regex
  output_file      = var.output_file
  parent_folder_id = var.parent_folder_id
  query_keyword    = var.query_keyword
}
```

[top](#index)

### Outputs

```terraform
output "folders" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_folders.this.folders
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_folders.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_folders.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_folders.this.names
}

output "this" {
  value = alicloud_resource_manager_folders.this
}
```

[top](#index)