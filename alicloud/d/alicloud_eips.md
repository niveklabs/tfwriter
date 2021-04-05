# alicloud_eips

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
module "alicloud_eips" {
  source = "./modules/alicloud/d/alicloud_eips"

  # ids - (optional) is a type of list of string
  ids = []
  # in_use - (optional) is a type of bool
  in_use = null
  # ip_addresses - (optional) is a type of list of string
  ip_addresses = []
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "in_use" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_addresses" {
  description = "(optional)"
  type        = list(string)
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_eips" "this" {
  ids               = var.ids
  in_use            = var.in_use
  ip_addresses      = var.ip_addresses
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "eips" {
  description = "returns a list of object"
  value       = data.alicloud_eips.this.eips
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_eips.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_eips.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_eips.this.names
}

output "this" {
  value = alicloud_eips.this
}
```

[top](#index)