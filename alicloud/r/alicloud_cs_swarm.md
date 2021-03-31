# alicloud_cs_swarm

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
module "alicloud_cs_swarm" {
  source = "./modules/alicloud/r/alicloud_cs_swarm"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # disk_category - (optional) is a type of string
  disk_category = null
  # disk_size - (optional) is a type of number
  disk_size = null
  # image_id - (optional) is a type of string
  image_id = null
  # instance_type - (required) is a type of string
  instance_type = null
  # is_outdated - (optional) is a type of bool
  is_outdated = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # need_slb - (optional) is a type of bool
  need_slb = null
  # node_number - (optional) is a type of number
  node_number = null
  # password - (required) is a type of string
  password = null
  # release_eip - (optional) is a type of bool
  release_eip = null
  # size - (optional) is a type of number
  size = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "is_outdated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "need_slb" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "node_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "release_eip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cs_swarm" "this" {
  cidr_block    = var.cidr_block
  disk_category = var.disk_category
  disk_size     = var.disk_size
  image_id      = var.image_id
  instance_type = var.instance_type
  is_outdated   = var.is_outdated
  name          = var.name
  name_prefix   = var.name_prefix
  need_slb      = var.need_slb
  node_number   = var.node_number
  password      = var.password
  release_eip   = var.release_eip
  size          = var.size
  vswitch_id    = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "agent_version" {
  description = "returns a string"
  value       = alicloud_cs_swarm.this.agent_version
}

output "id" {
  description = "returns a string"
  value       = alicloud_cs_swarm.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_cs_swarm.this.name
}

output "nodes" {
  description = "returns a list of object"
  value       = alicloud_cs_swarm.this.nodes
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_cs_swarm.this.security_group_id
}

output "slb_id" {
  description = "returns a string"
  value       = alicloud_cs_swarm.this.slb_id
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_cs_swarm.this.vpc_id
}

output "this" {
  value = alicloud_cs_swarm.this
}
```

[top](#index)