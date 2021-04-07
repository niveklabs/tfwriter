# alicloud_resource_manager_resource_directories

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
module "alicloud_resource_manager_resource_directories" {
  source = "./modules/alicloud/d/alicloud_resource_manager_resource_directories"

  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_resource_directories" "this" {
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "directories" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_resource_directories.this.directories
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_resource_directories.this.id
}

output "this" {
  value = alicloud_resource_manager_resource_directories.this
}
```

[top](#index)