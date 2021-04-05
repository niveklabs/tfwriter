# alicloud_slb

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
module "alicloud_slb" {
  source = "./modules/alicloud/r/alicloud_slb"

  # address - (optional) is a type of string
  address = null
  # address_ip_version - (optional) is a type of string
  address_ip_version = null
  # address_type - (optional) is a type of string
  address_type = null
  # bandwidth - (optional) is a type of number
  bandwidth = null
  # delete_protection - (optional) is a type of string
  delete_protection = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # internet - (optional) is a type of bool
  internet = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # master_zone_id - (optional) is a type of string
  master_zone_id = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # slave_zone_id - (optional) is a type of string
  slave_zone_id = null
  # specification - (optional) is a type of string
  specification = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "delete_protection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "slave_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "specification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb" "this" {
  address              = var.address
  address_ip_version   = var.address_ip_version
  address_type         = var.address_type
  bandwidth            = var.bandwidth
  delete_protection    = var.delete_protection
  instance_charge_type = var.instance_charge_type
  internet             = var.internet
  internet_charge_type = var.internet_charge_type
  master_zone_id       = var.master_zone_id
  name                 = var.name
  period               = var.period
  resource_group_id    = var.resource_group_id
  slave_zone_id        = var.slave_zone_id
  specification        = var.specification
  tags                 = var.tags
  vswitch_id           = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = alicloud_slb.this.address
}

output "address_type" {
  description = "returns a string"
  value       = alicloud_slb.this.address_type
}

output "id" {
  description = "returns a string"
  value       = alicloud_slb.this.id
}

output "internet" {
  description = "returns a bool"
  value       = alicloud_slb.this.internet
}

output "master_zone_id" {
  description = "returns a string"
  value       = alicloud_slb.this.master_zone_id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_slb.this.resource_group_id
}

output "slave_zone_id" {
  description = "returns a string"
  value       = alicloud_slb.this.slave_zone_id
}

output "this" {
  value = alicloud_slb.this
}
```

[top](#index)