# alicloud_vpn_gateway

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
module "alicloud_vpn_gateway" {
  source = "./modules/alicloud/r/alicloud_vpn_gateway"

  # bandwidth - (required) is a type of number
  bandwidth = null
  # description - (optional) is a type of string
  description = null
  # enable_ipsec - (optional) is a type of bool
  enable_ipsec = null
  # enable_ssl - (optional) is a type of bool
  enable_ssl = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # ssl_connections - (optional) is a type of number
  ssl_connections = null
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_ipsec" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ssl" {
  description = "(optional)"
  type        = bool
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

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_connections" {
  description = "(optional)"
  type        = number
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
```

[top](#index)

### Resource

```terraform
resource "alicloud_vpn_gateway" "this" {
  bandwidth            = var.bandwidth
  description          = var.description
  enable_ipsec         = var.enable_ipsec
  enable_ssl           = var.enable_ssl
  instance_charge_type = var.instance_charge_type
  name                 = var.name
  period               = var.period
  ssl_connections      = var.ssl_connections
  vpc_id               = var.vpc_id
  vswitch_id           = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "business_status" {
  description = "returns a string"
  value       = alicloud_vpn_gateway.this.business_status
}

output "id" {
  description = "returns a string"
  value       = alicloud_vpn_gateway.this.id
}

output "internet_ip" {
  description = "returns a string"
  value       = alicloud_vpn_gateway.this.internet_ip
}

output "name" {
  description = "returns a string"
  value       = alicloud_vpn_gateway.this.name
}

output "status" {
  description = "returns a string"
  value       = alicloud_vpn_gateway.this.status
}

output "vswitch_id" {
  description = "returns a string"
  value       = alicloud_vpn_gateway.this.vswitch_id
}

output "this" {
  value = alicloud_vpn_gateway.this
}
```

[top](#index)