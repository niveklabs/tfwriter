# alicloud_reserved_instance

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
module "alicloud_reserved_instance" {
  source = "./modules/alicloud/r/alicloud_reserved_instance"

  # description - (optional) is a type of string
  description = null
  # instance_amount - (optional) is a type of number
  instance_amount = null
  # instance_type - (required) is a type of string
  instance_type = null
  # name - (optional) is a type of string
  name = null
  # offering_type - (optional) is a type of string
  offering_type = null
  # period - (optional) is a type of number
  period = null
  # period_unit - (optional) is a type of string
  period_unit = null
  # platform - (optional) is a type of string
  platform = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # scope - (optional) is a type of string
  scope = null
  # zone_id - (optional) is a type of string
  zone_id = null
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

variable "instance_amount" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "offering_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "period_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_reserved_instance" "this" {
  description       = var.description
  instance_amount   = var.instance_amount
  instance_type     = var.instance_type
  name              = var.name
  offering_type     = var.offering_type
  period            = var.period
  period_unit       = var.period_unit
  platform          = var.platform
  resource_group_id = var.resource_group_id
  scope             = var.scope
  zone_id           = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_reserved_instance.this.id
}

output "instance_amount" {
  description = "returns a number"
  value       = alicloud_reserved_instance.this.instance_amount
}

output "platform" {
  description = "returns a string"
  value       = alicloud_reserved_instance.this.platform
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_reserved_instance.this.resource_group_id
}

output "this" {
  value = alicloud_reserved_instance.this
}
```

[top](#index)