# tencentcloud_vpn_gateway

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_vpn_gateway" {
  source = "./modules/tencentcloud/r/tencentcloud_vpn_gateway"

  # bandwidth - (optional) is a type of number
  bandwidth = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # name - (required) is a type of string
  name = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # prepaid_renew_flag - (optional) is a type of string
  prepaid_renew_flag = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(optional) - The maximum public network output bandwidth of VPN gateway (unit: Mbps), the available values include: 5,10,20,50,100,200,500,1000. Default is 5. When charge type is `PREPAID`, bandwidth degradation operation is unsupported."
  type        = number
  default     = null
}

variable "charge_type" {
  description = "(optional) - Charge Type of the VPN gateway. Valid value: `PREPAID`, `POSTPAID_BY_HOUR`. The default is `POSTPAID_BY_HOUR`."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the VPN gateway. The length of character is limited to 1-60."
  type        = string
}

variable "prepaid_period" {
  description = "(optional) - Period of instance to be prepaid. Valid value: `1`, `2`, `3`, `4`, `6`, `7`, `8`, `9`, `12`, `24`, `36`. The unit is month. Caution: when this para and renew_flag para are valid, the request means to renew several months more pre-paid period. This para can only be set to take effect in create operation."
  type        = number
  default     = null
}

variable "prepaid_renew_flag" {
  description = "(optional) - Flag indicates whether to renew or not. Valid value: `NOTIFY_AND_RENEW`, `NOTIFY_AND_AUTO_RENEW`, `NOT_NOTIFY_AND_NOT_RENEW`. This para can only be set to take effect in create operation."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tags used to associate different resources."
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - Type of gateway instance. Valid value: `IPSEC`, `SSL` and `CCN`. Note: CCN type is only for whitelist customer now."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC. Required if vpn gateway is not in `CCN` type, and doesn't make sense for `CCN` vpn gateway."
  type        = string
  default     = null
}

variable "zone" {
  description = "(required) - Zone of the VPN gateway."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vpn_gateway" "this" {
  bandwidth          = var.bandwidth
  charge_type        = var.charge_type
  name               = var.name
  prepaid_period     = var.prepaid_period
  prepaid_renew_flag = var.prepaid_renew_flag
  tags               = var.tags
  type               = var.type
  vpc_id             = var.vpc_id
  zone               = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.create_time
}

output "expired_time" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.expired_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.id
}

output "is_address_blocked" {
  description = "returns a bool"
  value       = tencentcloud_vpn_gateway.this.is_address_blocked
}

output "new_purchase_plan" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.new_purchase_plan
}

output "public_ip_address" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.public_ip_address
}

output "restrict_state" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.restrict_state
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.state
}

output "type" {
  description = "returns a string"
  value       = tencentcloud_vpn_gateway.this.type
}

output "this" {
  value = tencentcloud_vpn_gateway.this
}
```

[top](#index)