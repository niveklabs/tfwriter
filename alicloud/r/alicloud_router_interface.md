# alicloud_router_interface

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
module "alicloud_router_interface" {
  source = "./modules/alicloud/r/alicloud_router_interface"

  # description - (optional) is a type of string
  description = null
  # health_check_source_ip - (optional) is a type of string
  health_check_source_ip = null
  # health_check_target_ip - (optional) is a type of string
  health_check_target_ip = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # name - (optional) is a type of string
  name = null
  # opposite_access_point_id - (optional) is a type of string
  opposite_access_point_id = null
  # opposite_region - (required) is a type of string
  opposite_region = null
  # period - (optional) is a type of number
  period = null
  # role - (required) is a type of string
  role = null
  # router_id - (required) is a type of string
  router_id = null
  # router_type - (required) is a type of string
  router_type = null
  # specification - (optional) is a type of string
  specification = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_target_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opposite_access_point_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opposite_region" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "router_id" {
  description = "(required)"
  type        = string
}

variable "router_type" {
  description = "(required)"
  type        = string
}

variable "specification" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_router_interface" "this" {
  description              = var.description
  health_check_source_ip   = var.health_check_source_ip
  health_check_target_ip   = var.health_check_target_ip
  instance_charge_type     = var.instance_charge_type
  name                     = var.name
  opposite_access_point_id = var.opposite_access_point_id
  opposite_region          = var.opposite_region
  period                   = var.period
  role                     = var.role
  router_id                = var.router_id
  router_type              = var.router_type
  specification            = var.specification
}
```

[top](#index)

### Outputs

```terraform
output "access_point_id" {
  description = "returns a string"
  value       = alicloud_router_interface.this.access_point_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_router_interface.this.id
}

output "opposite_interface_id" {
  description = "returns a string"
  value       = alicloud_router_interface.this.opposite_interface_id
}

output "opposite_interface_owner_id" {
  description = "returns a string"
  value       = alicloud_router_interface.this.opposite_interface_owner_id
}

output "opposite_router_id" {
  description = "returns a string"
  value       = alicloud_router_interface.this.opposite_router_id
}

output "opposite_router_type" {
  description = "returns a string"
  value       = alicloud_router_interface.this.opposite_router_type
}

output "this" {
  value = alicloud_router_interface.this
}
```

[top](#index)