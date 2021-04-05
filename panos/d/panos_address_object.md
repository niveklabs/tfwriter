# panos_address_object

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
module "panos_address_object" {
  source = "./modules/panos/d/panos_address_object"

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
  description = "(required)"
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
data "panos_address_object" "this" {
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
  value       = data.panos_address_object.this.description
}

output "id" {
  description = "returns a string"
  value       = data.panos_address_object.this.id
}

output "tags" {
  description = "returns a list of string"
  value       = data.panos_address_object.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.panos_address_object.this.type
}

output "value" {
  description = "returns a string"
  value       = data.panos_address_object.this.value
}

output "this" {
  value = panos_address_object.this
}
```

[top](#index)