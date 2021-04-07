# tencentcloud_eip

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
module "tencentcloud_eip" {
  source = "./modules/tencentcloud/r/tencentcloud_eip"

  # anycast_zone - (optional) is a type of string
  anycast_zone = null
  # applicable_for_clb - (optional) is a type of bool
  applicable_for_clb = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = null
  # internet_service_provider - (optional) is a type of string
  internet_service_provider = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "anycast_zone" {
  description = "(optional) - The zone of anycast. Valid value: `ANYCAST_ZONE_GLOBAL` and `ANYCAST_ZONE_OVERSEAS`."
  type        = string
  default     = null
}

variable "applicable_for_clb" {
  description = "(optional) - Indicates whether the anycast eip can be associated to a CLB."
  type        = bool
  default     = null
}

variable "internet_charge_type" {
  description = "(optional) - The charge type of eip. Valid value: `BANDWIDTH_PACKAGE`, `BANDWIDTH_POSTPAID_BY_HOUR` and `TRAFFIC_POSTPAID_BY_HOUR`."
  type        = string
  default     = null
}

variable "internet_max_bandwidth_out" {
  description = "(optional) - The bandwidth limit of EIP, unit is Mbps."
  type        = number
  default     = null
}

variable "internet_service_provider" {
  description = "(optional) - Internet service provider of eip. Valid value: `BGP`, `CMCC`, `CTCC` and `CUCC`."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of eip."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags of eip."
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - The type of eip. Valid value:  `EIP` and `AnycastEIP`. Default is `EIP`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_eip" "this" {
  anycast_zone               = var.anycast_zone
  applicable_for_clb         = var.applicable_for_clb
  internet_charge_type       = var.internet_charge_type
  internet_max_bandwidth_out = var.internet_max_bandwidth_out
  internet_service_provider  = var.internet_service_provider
  name                       = var.name
  tags                       = var.tags
  type                       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_eip.this.id
}

output "name" {
  description = "returns a string"
  value       = tencentcloud_eip.this.name
}

output "public_ip" {
  description = "returns a string"
  value       = tencentcloud_eip.this.public_ip
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_eip.this.status
}

output "this" {
  value = tencentcloud_eip.this
}
```

[top](#index)