# alicloud_resource_manager_folder

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
module "alicloud_resource_manager_folder" {
  source = "./modules/alicloud/r/alicloud_resource_manager_folder"

  # folder_name - (required) is a type of string
  folder_name = null
  # parent_folder_id - (optional) is a type of string
  parent_folder_id = null
}
```

[top](#index)

### Variables

```terraform
variable "folder_name" {
  description = "(required)"
  type        = string
}

variable "parent_folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_folder" "this" {
  folder_name      = var.folder_name
  parent_folder_id = var.parent_folder_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_folder.this.id
}

output "parent_folder_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_folder.this.parent_folder_id
}

output "this" {
  value = alicloud_resource_manager_folder.this
}
```

[top](#index)