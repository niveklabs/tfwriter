# alicloud_eip

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
module "alicloud_eip" {
  source = "./modules/alicloud/r/alicloud_eip"

  # bandwidth - (optional) is a type of number
  bandwidth = null
  # description - (optional) is a type of string
  description = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # isp - (optional) is a type of string
  isp = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isp" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_eip" "this" {
  bandwidth            = var.bandwidth
  description          = var.description
  instance_charge_type = var.instance_charge_type
  internet_charge_type = var.internet_charge_type
  isp                  = var.isp
  name                 = var.name
  period               = var.period
  resource_group_id    = var.resource_group_id
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_eip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = alicloud_eip.this.ip_address
}

output "isp" {
  description = "returns a string"
  value       = alicloud_eip.this.isp
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_eip.this.resource_group_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_eip.this.status
}

output "this" {
  value = alicloud_eip.this
}
```

[top](#index)