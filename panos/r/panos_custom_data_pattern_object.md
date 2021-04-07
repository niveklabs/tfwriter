# panos_custom_data_pattern_object

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_custom_data_pattern_object" {
  source = "./modules/panos/r/panos_custom_data_pattern_object"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
  # vsys - (optional) is a type of string
  vsys = null

  file_property = [{
    file_property  = null
    file_type      = null
    name           = null
    property_value = null
  }]

  predefined_pattern = [{
    file_types = []
    name       = null
  }]

  regex = [{
    file_types = []
    name       = null
    regex      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "type" {
  description = "(optional) - Type"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_property" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      file_property  = string
      file_type      = string
      name           = string
      property_value = string
    }
  ))
  default = []
}

variable "predefined_pattern" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      file_types = list(string)
      name       = string
    }
  ))
  default = []
}

variable "regex" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      file_types = list(string)
      name       = string
      regex      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_custom_data_pattern_object" "this" {
  # description - (optional) is a type of string
  description = var.description
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # type - (optional) is a type of string
  type = var.type
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "file_property" {
    for_each = var.file_property
    content {
      # file_property - (required) is a type of string
      file_property = file_property.value["file_property"]
      # file_type - (required) is a type of string
      file_type = file_property.value["file_type"]
      # name - (required) is a type of string
      name = file_property.value["name"]
      # property_value - (required) is a type of string
      property_value = file_property.value["property_value"]
    }
  }

  dynamic "predefined_pattern" {
    for_each = var.predefined_pattern
    content {
      # file_types - (optional) is a type of list of string
      file_types = predefined_pattern.value["file_types"]
      # name - (required) is a type of string
      name = predefined_pattern.value["name"]
    }
  }

  dynamic "regex" {
    for_each = var.regex
    content {
      # file_types - (optional) is a type of list of string
      file_types = regex.value["file_types"]
      # name - (required) is a type of string
      name = regex.value["name"]
      # regex - (required) is a type of string
      regex = regex.value["regex"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_custom_data_pattern_object.this.id
}

output "this" {
  value = panos_custom_data_pattern_object.this
}
```

[top](#index)