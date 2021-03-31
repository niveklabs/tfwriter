# alicloud_nat_gateway

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
module "alicloud_nat_gateway" {
  source = "./modules/alicloud/r/alicloud_nat_gateway"

  # description - (optional) is a type of string
  description = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # name - (optional) is a type of string
  name = null
  # nat_type - (optional) is a type of string
  nat_type = null
  # period - (optional) is a type of number
  period = null
  # spec - (optional) is a type of string
  spec = null
  # specification - (optional) is a type of string
  specification = null
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null

  bandwidth_packages = [{
    bandwidth           = null
    ip_count            = null
    public_ip_addresses = null
    zone                = null
  }]
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

variable "nat_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "specification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bandwidth_packages" {
  description = "nested block: NestingList, min items: 0, max items: 4"
  type = set(object(
    {
      bandwidth           = number
      ip_count            = number
      public_ip_addresses = string
      zone                = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_nat_gateway" "this" {
  description          = var.description
  instance_charge_type = var.instance_charge_type
  name                 = var.name
  nat_type             = var.nat_type
  period               = var.period
  spec                 = var.spec
  specification        = var.specification
  vpc_id               = var.vpc_id
  vswitch_id           = var.vswitch_id

  dynamic "bandwidth_packages" {
    for_each = var.bandwidth_packages
    content {
      bandwidth = bandwidth_packages.value["bandwidth"]
      ip_count  = bandwidth_packages.value["ip_count"]
      zone      = bandwidth_packages.value["zone"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_package_ids" {
  description = "returns a string"
  value       = alicloud_nat_gateway.this.bandwidth_package_ids
}

output "forward_table_ids" {
  description = "returns a string"
  value       = alicloud_nat_gateway.this.forward_table_ids
}

output "id" {
  description = "returns a string"
  value       = alicloud_nat_gateway.this.id
}

output "instance_charge_type" {
  description = "returns a string"
  value       = alicloud_nat_gateway.this.instance_charge_type
}

output "name" {
  description = "returns a string"
  value       = alicloud_nat_gateway.this.name
}

output "snat_table_ids" {
  description = "returns a string"
  value       = alicloud_nat_gateway.this.snat_table_ids
}

output "this" {
  value = alicloud_nat_gateway.this
}
```

[top](#index)