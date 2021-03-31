# alicloud_slbs

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slbs" {
  source = "./modules/alicloud/d/alicloud_slbs"

  # address - (optional) is a type of string
  address = null
  # ids - (optional) is a type of list of string
  ids = []
  # master_availability_zone - (optional) is a type of string
  master_availability_zone = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # network_type - (optional) is a type of string
  network_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # slave_availability_zone - (optional) is a type of string
  slave_availability_zone = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "master_availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_type" {
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

variable "slave_availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
data "alicloud_slbs" "this" {
  address                  = var.address
  ids                      = var.ids
  master_availability_zone = var.master_availability_zone
  name_regex               = var.name_regex
  network_type             = var.network_type
  output_file              = var.output_file
  resource_group_id        = var.resource_group_id
  slave_availability_zone  = var.slave_availability_zone
  tags                     = var.tags
  vpc_id                   = var.vpc_id
  vswitch_id               = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_slbs.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_slbs.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_slbs.this.names
}

output "slbs" {
  description = "returns a list of object"
  value       = data.alicloud_slbs.this.slbs
}

output "this" {
  value = alicloud_slbs.this
}
```

[top](#index)