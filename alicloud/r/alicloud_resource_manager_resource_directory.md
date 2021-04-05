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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_resource_directory" {
  source = "./modules/alicloud/r/alicloud_resource_manager_resource_directory"

  # status - (optional) is a type of string
  status = null

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_resource_directory" "this" {
  status = var.status

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      update = timeouts.value["update"]
    }
  }

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