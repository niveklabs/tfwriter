# alicloud_resource_manager_handshake

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
module "alicloud_resource_manager_handshake" {
  source = "./modules/alicloud/r/alicloud_resource_manager_handshake"

  # note - (optional) is a type of string
  note = null
  # target_entity - (required) is a type of string
  target_entity = null
  # target_type - (required) is a type of string
  target_type = null
}
```

[top](#index)

### Variables

```terraform
variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_entity" {
  description = "(required)"
  type        = string
}

variable "target_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_handshake" "this" {
  note          = var.note
  target_entity = var.target_entity
  target_type   = var.target_type
}
```

[top](#index)

### Outputs

```terraform
output "expire_time" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.expire_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.id
}

output "master_account_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.master_account_id
}

output "master_account_name" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.master_account_name
}

output "modify_time" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.modify_time
}

output "resource_directory_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.resource_directory_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_resource_manager_handshake.this.status
}

output "this" {
  value = alicloud_resource_manager_handshake.this
}
```

[top](#index)