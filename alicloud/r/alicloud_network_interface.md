# alicloud_network_interface

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
module "alicloud_network_interface" {
  source = "./modules/alicloud/r/alicloud_network_interface"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # private_ips - (optional) is a type of set of string
  private_ips = []
  # private_ips_count - (optional) is a type of number
  private_ips_count = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_groups - (required) is a type of set of string
  security_groups = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (required) is a type of string
  vswitch_id = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "private_ips_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "alicloud_network_interface" "this" {
  description       = var.description
  name              = var.name
  private_ip        = var.private_ip
  private_ips       = var.private_ips
  private_ips_count = var.private_ips_count
  resource_group_id = var.resource_group_id
  security_groups   = var.security_groups
  tags              = var.tags
  vswitch_id        = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_network_interface.this.id
}

output "mac" {
  description = "returns a string"
  value       = alicloud_network_interface.this.mac
}

output "private_ip" {
  description = "returns a string"
  value       = alicloud_network_interface.this.private_ip
}

output "private_ips" {
  description = "returns a set of string"
  value       = alicloud_network_interface.this.private_ips
}

output "private_ips_count" {
  description = "returns a number"
  value       = alicloud_network_interface.this.private_ips_count
}

output "this" {
  value = alicloud_network_interface.this
}
```

[top](#index)