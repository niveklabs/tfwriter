# fortios_firewall_shapingprofile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_shapingprofile" {
  source = "./modules/fortios/r/fortios_firewall_shapingprofile"

  # comment - (optional) is a type of string
  comment = null
  # default_class_id - (required) is a type of number
  default_class_id = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # profile_name - (required) is a type of string
  profile_name = null
  # type - (optional) is a type of string
  type = null

  shaping_entries = [{
    burst_in_msec                   = null
    cburst_in_msec                  = null
    class_id                        = null
    guaranteed_bandwidth_percentage = null
    id                              = null
    limit                           = null
    max                             = null
    maximum_bandwidth_percentage    = null
    min                             = null
    priority                        = null
    red_probability                 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_class_id" {
  description = "(required)"
  type        = number
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shaping_entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      burst_in_msec                   = number
      cburst_in_msec                  = number
      class_id                        = number
      guaranteed_bandwidth_percentage = number
      id                              = number
      limit                           = number
      max                             = number
      maximum_bandwidth_percentage    = number
      min                             = number
      priority                        = string
      red_probability                 = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_shapingprofile" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # default_class_id - (required) is a type of number
  default_class_id = var.default_class_id
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # profile_name - (required) is a type of string
  profile_name = var.profile_name
  # type - (optional) is a type of string
  type = var.type

  dynamic "shaping_entries" {
    for_each = var.shaping_entries
    content {
      # burst_in_msec - (optional) is a type of number
      burst_in_msec = shaping_entries.value["burst_in_msec"]
      # cburst_in_msec - (optional) is a type of number
      cburst_in_msec = shaping_entries.value["cburst_in_msec"]
      # class_id - (optional) is a type of number
      class_id = shaping_entries.value["class_id"]
      # guaranteed_bandwidth_percentage - (optional) is a type of number
      guaranteed_bandwidth_percentage = shaping_entries.value["guaranteed_bandwidth_percentage"]
      # id - (optional) is a type of number
      id = shaping_entries.value["id"]
      # limit - (optional) is a type of number
      limit = shaping_entries.value["limit"]
      # max - (optional) is a type of number
      max = shaping_entries.value["max"]
      # maximum_bandwidth_percentage - (optional) is a type of number
      maximum_bandwidth_percentage = shaping_entries.value["maximum_bandwidth_percentage"]
      # min - (optional) is a type of number
      min = shaping_entries.value["min"]
      # priority - (optional) is a type of string
      priority = shaping_entries.value["priority"]
      # red_probability - (optional) is a type of number
      red_probability = shaping_entries.value["red_probability"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_shapingprofile.this.id
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_shapingprofile.this.type
}

output "this" {
  value = fortios_firewall_shapingprofile.this
}
```

[top](#index)