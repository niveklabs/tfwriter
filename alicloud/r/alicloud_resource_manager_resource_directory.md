# alicloud_resource_manager_resource_directory

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_resource_directory" {
  source = "./modules/alicloud/r/alicloud_resource_manager_resource_directory"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_resource_directory" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_directory.this.id
}

output "master_account_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_directory.this.master_account_id
}

output "master_account_name" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_directory.this.master_account_name
}

output "root_folder_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_resource_directory.this.root_folder_id
}

output "this" {
  value = alicloud_resource_manager_resource_directory.this
}
```

[top](#index)