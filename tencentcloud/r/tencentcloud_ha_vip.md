# tencentcloud_ha_vip

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
module "tencentcloud_ha_vip" {
  source = "./modules/tencentcloud/r/tencentcloud_ha_vip"

  # name - (required) is a type of string
  name = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # vip - (optional) is a type of string
  vip = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the HA VIP. The length of character is limited to 1-60."
  type        = string
}

variable "subnet_id" {
  description = "(required) - Subnet ID."
  type        = string
}

variable "vip" {
  description = "(optional) - Virtual IP address, it must not be occupied and in this VPC network segment. If not set, it will be assigned after resource created automatically."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required) - VPC ID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ha_vip" "this" {
  # name - (required) is a type of string
  name = var.name
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # vip - (optional) is a type of string
  vip = var.vip
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "address_ip" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.address_ip
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.instance_id
}

output "network_interface_id" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.network_interface_id
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.state
}

output "vip" {
  description = "returns a string"
  value       = tencentcloud_ha_vip.this.vip
}

output "this" {
  value = tencentcloud_ha_vip.this
}
```

[top](#index)