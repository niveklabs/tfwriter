# fortios_application_name

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
module "fortios_application_name" {
  source = "./modules/fortios/r/fortios_application_name"

  # behavior - (optional) is a type of string
  behavior = null
  # category - (required) is a type of number
  category = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null
  # parameter - (optional) is a type of string
  parameter = null
  # popularity - (optional) is a type of number
  popularity = null
  # protocol - (optional) is a type of string
  protocol = null
  # risk - (optional) is a type of number
  risk = null
  # sub_category - (optional) is a type of number
  sub_category = null
  # technology - (optional) is a type of string
  technology = null
  # vendor - (optional) is a type of string
  vendor = null
  # weight - (optional) is a type of number
  weight = null

  metadata = [{
    id      = null
    metaid  = null
    valueid = null
  }]

  parameters = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(required)"
  type        = number
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "popularity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "risk" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sub_category" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "technology" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metadata" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id      = number
      metaid  = number
      valueid = number
    }
  ))
  default = []
}

variable "parameters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_application_name" "this" {
  # behavior - (optional) is a type of string
  behavior = var.behavior
  # category - (required) is a type of number
  category = var.category
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # name - (optional) is a type of string
  name = var.name
  # parameter - (optional) is a type of string
  parameter = var.parameter
  # popularity - (optional) is a type of number
  popularity = var.popularity
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # risk - (optional) is a type of number
  risk = var.risk
  # sub_category - (optional) is a type of number
  sub_category = var.sub_category
  # technology - (optional) is a type of string
  technology = var.technology
  # vendor - (optional) is a type of string
  vendor = var.vendor
  # weight - (optional) is a type of number
  weight = var.weight

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # id - (optional) is a type of number
      id = metadata.value["id"]
      # metaid - (optional) is a type of number
      metaid = metadata.value["metaid"]
      # valueid - (optional) is a type of number
      valueid = metadata.value["valueid"]
    }
  }

  dynamic "parameters" {
    for_each = var.parameters
    content {
      # name - (optional) is a type of string
      name = parameters.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "behavior" {
  description = "returns a string"
  value       = fortios_application_name.this.behavior
}

output "fosid" {
  description = "returns a number"
  value       = fortios_application_name.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_application_name.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_application_name.this.name
}

output "parameter" {
  description = "returns a string"
  value       = fortios_application_name.this.parameter
}

output "popularity" {
  description = "returns a number"
  value       = fortios_application_name.this.popularity
}

output "protocol" {
  description = "returns a string"
  value       = fortios_application_name.this.protocol
}

output "risk" {
  description = "returns a number"
  value       = fortios_application_name.this.risk
}

output "sub_category" {
  description = "returns a number"
  value       = fortios_application_name.this.sub_category
}

output "technology" {
  description = "returns a string"
  value       = fortios_application_name.this.technology
}

output "vendor" {
  description = "returns a string"
  value       = fortios_application_name.this.vendor
}

output "weight" {
  description = "returns a number"
  value       = fortios_application_name.this.weight
}

output "this" {
  value = fortios_application_name.this
}
```

[top](#index)