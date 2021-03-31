# alicloud_eci_container_groups

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
module "alicloud_eci_container_groups" {
  source = "./modules/alicloud/d/alicloud_eci_container_groups"

  # container_group_name - (optional) is a type of string
  container_group_name = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # limit - (optional) is a type of number
  limit = null
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
  # with_event - (optional) is a type of bool
  with_event = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "container_group_name" {
  description = "(optional)"
  type        = string
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

variable "limit" {
  description = "(optional)"
  type        = number
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

variable "with_event" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_eci_container_groups" "this" {
  container_group_name = var.container_group_name
  enable_details       = var.enable_details
  ids                  = var.ids
  limit                = var.limit
  name_regex           = var.name_regex
  output_file          = var.output_file
  resource_group_id    = var.resource_group_id
  status               = var.status
  tags                 = var.tags
  vswitch_id           = var.vswitch_id
  with_event           = var.with_event
  zone_id              = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.alicloud_eci_container_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_eci_container_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_eci_container_groups.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_eci_container_groups.this.names
}

output "this" {
  value = alicloud_eci_container_groups.this
}
```

[top](#index)