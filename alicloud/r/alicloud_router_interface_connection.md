# alicloud_router_interface_connection

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
module "alicloud_router_interface_connection" {
  source = "./modules/alicloud/r/alicloud_router_interface_connection"

  # interface_id - (required) is a type of string
  interface_id = null
  # opposite_interface_id - (required) is a type of string
  opposite_interface_id = null
  # opposite_interface_owner_id - (optional) is a type of string
  opposite_interface_owner_id = null
  # opposite_router_id - (optional) is a type of string
  opposite_router_id = null
  # opposite_router_type - (optional) is a type of string
  opposite_router_type = null
}
```

[top](#index)

### Variables

```terraform
variable "interface_id" {
  description = "(required)"
  type        = string
}

variable "opposite_interface_id" {
  description = "(required)"
  type        = string
}

variable "opposite_interface_owner_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opposite_router_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opposite_router_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_router_interface_connection" "this" {
  interface_id                = var.interface_id
  opposite_interface_id       = var.opposite_interface_id
  opposite_interface_owner_id = var.opposite_interface_owner_id
  opposite_router_id          = var.opposite_router_id
  opposite_router_type        = var.opposite_router_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_router_interface_connection.this.id
}

output "opposite_interface_owner_id" {
  description = "returns a string"
  value       = alicloud_router_interface_connection.this.opposite_interface_owner_id
}

output "opposite_router_id" {
  description = "returns a string"
  value       = alicloud_router_interface_connection.this.opposite_router_id
}

output "this" {
  value = alicloud_router_interface_connection.this
}
```

[top](#index)