# alicloud_network_interfaces

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_network_interfaces" {
  source = "./modules/alicloud/d/alicloud_network_interfaces"

  # ids - (optional) is a type of set of string
  ids = []
  # instance_id - (optional) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_network_interfaces" "this" {
  # ids - (optional) is a type of set of string
  ids = var.ids
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # private_ip - (optional) is a type of string
  private_ip = var.private_ip
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_network_interfaces.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.alicloud_network_interfaces.this.ids
}

output "interfaces" {
  description = "returns a list of object"
  value       = data.alicloud_network_interfaces.this.interfaces
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_network_interfaces.this.names
}

output "this" {
  value = alicloud_network_interfaces.this
}
```

[top](#index)