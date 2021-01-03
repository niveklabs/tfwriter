# alicloud_vpcs

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_vpcs" {
  source = "./modules/alicloud/d/alicloud_vpcs"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # ids - (optional) is a type of list of string
  ids = []
  # is_default - (optional) is a type of bool
  is_default = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "is_default" {
  description = "(optional)"
  type        = bool
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

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
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

### Datasource

```terraform
data "alicloud_vpcs" "this" {
  cidr_block        = var.cidr_block
  ids               = var.ids
  is_default        = var.is_default
  name_regex        = var.name_regex
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
  status            = var.status
  tags              = var.tags
  vswitch_id        = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_vpcs.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_vpcs.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_vpcs.this.names
}

output "vpcs" {
  description = "returns a list of object"
  value       = data.alicloud_vpcs.this.vpcs
}

output "this" {
  value = alicloud_vpcs.this
}
```

[top](#index)