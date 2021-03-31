# panos_panorama_address_object

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_address_object" {
  source = "./modules/panos/r/panos_panorama_address_object"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
  # type - (optional) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_address_object" "this" {
  description  = var.description
  device_group = var.device_group
  name         = var.name
  tags         = var.tags
  type         = var.type
  value        = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_address_object.this.id
}

output "this" {
  value = panos_panorama_address_object.this
}
```

[top](#index)