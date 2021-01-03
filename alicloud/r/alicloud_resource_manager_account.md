# alicloud_resource_manager_account

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
module "alicloud_resource_manager_account" {
  source = "./modules/alicloud/r/alicloud_resource_manager_account"

  # display_name - (required) is a type of string
  display_name = null
  # folder_id - (optional) is a type of string
  folder_id = null
  # payer_account_id - (optional) is a type of string
  payer_account_id = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(required)"
  type        = string
}

variable "folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payer_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_account" "this" {
  display_name     = var.display_name
  folder_id        = var.folder_id
  payer_account_id = var.payer_account_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.id
}

output "join_method" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.join_method
}

output "join_time" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.join_time
}

output "modify_time" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.modify_time
}

output "resource_directory_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.resource_directory_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.status
}

output "type" {
  description = "returns a string"
  value       = alicloud_resource_manager_account.this.type
}

output "this" {
  value = alicloud_resource_manager_account.this
}
```

[top](#index)