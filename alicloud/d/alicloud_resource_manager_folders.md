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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_folders" {
  source = "./modules/alicloud/d/alicloud_resource_manager_folders"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # parent_folder_id - (optional) is a type of string
  parent_folder_id = null
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

variable "parent_folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_folders" "this" {
  ids              = var.ids
  name_regex       = var.name_regex
  output_file      = var.output_file
  parent_folder_id = var.parent_folder_id
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