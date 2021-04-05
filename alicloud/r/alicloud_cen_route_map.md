# alicloud_cen_route_map

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cen_route_map" {
  source = "./modules/alicloud/r/alicloud_cen_route_map"

  # as_path_match_mode - (optional) is a type of string
  as_path_match_mode = null
  # cen_id - (required) is a type of string
  cen_id = null
  # cen_region_id - (required) is a type of string
  cen_region_id = null
  # cidr_match_mode - (optional) is a type of string
  cidr_match_mode = null
  # community_match_mode - (optional) is a type of string
  community_match_mode = null
  # community_operate_mode - (optional) is a type of string
  community_operate_mode = null
  # description - (optional) is a type of string
  description = null
  # destination_child_instance_types - (optional) is a type of set of string
  destination_child_instance_types = []
  # destination_cidr_blocks - (optional) is a type of set of string
  destination_cidr_blocks = []
  # destination_instance_ids - (optional) is a type of set of string
  destination_instance_ids = []
  # destination_instance_ids_reverse_match - (optional) is a type of bool
  destination_instance_ids_reverse_match = null
  # destination_route_table_ids - (optional) is a type of set of string
  destination_route_table_ids = []
  # map_result - (required) is a type of string
  map_result = null
  # match_asns - (optional) is a type of set of string
  match_asns = []
  # match_community_set - (optional) is a type of set of string
  match_community_set = []
  # next_priority - (optional) is a type of number
  next_priority = null
  # operate_community_set - (optional) is a type of set of string
  operate_community_set = []
  # preference - (optional) is a type of number
  preference = null
  # prepend_as_path - (optional) is a type of set of string
  prepend_as_path = []
  # priority - (required) is a type of number
  priority = null
  # route_types - (optional) is a type of set of string
  route_types = []
  # source_child_instance_types - (optional) is a type of set of string
  source_child_instance_types = []
  # source_instance_ids - (optional) is a type of set of string
  source_instance_ids = []
  # source_instance_ids_reverse_match - (optional) is a type of bool
  source_instance_ids_reverse_match = null
  # source_region_ids - (optional) is a type of set of string
  source_region_ids = []
  # source_route_table_ids - (optional) is a type of set of string
  source_route_table_ids = []
  # transmit_direction - (required) is a type of string
  transmit_direction = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "as_path_match_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "cen_region_id" {
  description = "(required)"
  type        = string
}

variable "cidr_match_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "community_match_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "community_operate_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_child_instance_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination_cidr_blocks" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination_instance_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "destination_instance_ids_reverse_match" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "destination_route_table_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "map_result" {
  description = "(required)"
  type        = string
}

variable "match_asns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "match_community_set" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "next_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "operate_community_set" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "preference" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "prepend_as_path" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "route_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_child_instance_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_instance_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_instance_ids_reverse_match" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "source_region_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_route_table_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "transmit_direction" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_route_map" "this" {
  as_path_match_mode                     = var.as_path_match_mode
  cen_id                                 = var.cen_id
  cen_region_id                          = var.cen_region_id
  cidr_match_mode                        = var.cidr_match_mode
  community_match_mode                   = var.community_match_mode
  community_operate_mode                 = var.community_operate_mode
  description                            = var.description
  destination_child_instance_types       = var.destination_child_instance_types
  destination_cidr_blocks                = var.destination_cidr_blocks
  destination_instance_ids               = var.destination_instance_ids
  destination_instance_ids_reverse_match = var.destination_instance_ids_reverse_match
  destination_route_table_ids            = var.destination_route_table_ids
  map_result                             = var.map_result
  match_asns                             = var.match_asns
  match_community_set                    = var.match_community_set
  next_priority                          = var.next_priority
  operate_community_set                  = var.operate_community_set
  preference                             = var.preference
  prepend_as_path                        = var.prepend_as_path
  priority                               = var.priority
  route_types                            = var.route_types
  source_child_instance_types            = var.source_child_instance_types
  source_instance_ids                    = var.source_instance_ids
  source_instance_ids_reverse_match      = var.source_instance_ids_reverse_match
  source_region_ids                      = var.source_region_ids
  source_route_table_ids                 = var.source_route_table_ids
  transmit_direction                     = var.transmit_direction

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cen_route_map.this.id
}

output "route_map_id" {
  description = "returns a string"
  value       = alicloud_cen_route_map.this.route_map_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_cen_route_map.this.status
}

output "this" {
  value = alicloud_cen_route_map.this
}
```

[top](#index)