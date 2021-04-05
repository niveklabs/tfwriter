# panos_custom_data_pattern_object

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/panos/d/panos_custom_data_pattern_object"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_custom_data_pattern_object" "this" {
  device_group = var.device_group
  name         = var.name
  vsys         = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.panos_custom_data_pattern_object.this.description
}

output "file_property" {
  description = "returns a list of object"
  value       = data.panos_custom_data_pattern_object.this.file_property
}

output "id" {
  description = "returns a string"
  value       = data.panos_custom_data_pattern_object.this.id
}

output "predefined_pattern" {
  description = "returns a list of object"
  value       = data.panos_custom_data_pattern_object.this.predefined_pattern
}

output "regex" {
  description = "returns a list of object"
  value       = data.panos_custom_data_pattern_object.this.regex
}

output "type" {
  description = "returns a string"
  value       = data.panos_custom_data_pattern_object.this.type
}

output "this" {
  value = panos_custom_data_pattern_object.this
}
```

[top](#index)