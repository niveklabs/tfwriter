# panos_panorama_address_group

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
module "panos_panorama_address_group" {
  source = "./modules/panos/r/panos_panorama_address_group"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # dynamic_match - (optional) is a type of string
  dynamic_match = null
  # name - (required) is a type of string
  name = null
  # static_addresses - (optional) is a type of list of string
  static_addresses = []
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional) - The device group to put this address object in"
  type        = string
  default     = null
}

variable "dynamic_match" {
  description = "(optional) - Dynamic address group definition"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The address object's name"
  type        = string
}

variable "static_addresses" {
  description = "(optional) - Static address group entries"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Administrative tags for the address object"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_address_group" "this" {
  description      = var.description
  device_group     = var.device_group
  dynamic_match    = var.dynamic_match
  name             = var.name
  static_addresses = var.static_addresses
  tags             = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_address_group.this.id
}

output "this" {
  value = panos_panorama_address_group.this
}
```

[top](#index)