# alicloud_pvtz_zones

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
module "alicloud_pvtz_zones" {
  source = "./modules/alicloud/d/alicloud_pvtz_zones"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # keyword - (optional) is a type of string
  keyword = null
  # lang - (optional) is a type of string
  lang = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # query_region_id - (optional) is a type of string
  query_region_id = null
  # query_vpc_id - (optional) is a type of string
  query_vpc_id = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # search_mode - (optional) is a type of string
  search_mode = null
}
```

[top](#index)

### Variables

```terraform
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

variable "keyword" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lang" {
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

variable "query_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search_mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_pvtz_zones" "this" {
  enable_details    = var.enable_details
  ids               = var.ids
  keyword           = var.keyword
  lang              = var.lang
  name_regex        = var.name_regex
  output_file       = var.output_file
  query_region_id   = var.query_region_id
  query_vpc_id      = var.query_vpc_id
  resource_group_id = var.resource_group_id
  search_mode       = var.search_mode
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_pvtz_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_pvtz_zones.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_pvtz_zones.this.names
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_pvtz_zones.this.zones
}

output "this" {
  value = alicloud_pvtz_zones.this
}
```

[top](#index)