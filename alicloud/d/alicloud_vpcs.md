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
    alicloud = ">= 1.120.0"
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
  # dhcp_options_set_id - (optional) is a type of string
  dhcp_options_set_id = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # enable_details - (optional) is a type of bool
  enable_details = null
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
  # vpc_name - (optional) is a type of string
  vpc_name = null
  # vpc_owner_id - (optional) is a type of number
  vpc_owner_id = null
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

variable "dhcp_options_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
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

variable "vpc_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_owner_id" {
  description = "(optional)"
  type        = number
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
  cidr_block          = var.cidr_block
  dhcp_options_set_id = var.dhcp_options_set_id
  dry_run             = var.dry_run
  enable_details      = var.enable_details
  ids                 = var.ids
  is_default          = var.is_default
  name_regex          = var.name_regex
  output_file         = var.output_file
  resource_group_id   = var.resource_group_id
  status              = var.status
  tags                = var.tags
  vpc_name            = var.vpc_name
  vpc_owner_id        = var.vpc_owner_id
  vswitch_id          = var.vswitch_id
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