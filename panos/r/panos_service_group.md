# panos_service_group

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
module "panos_service_group" {
  source = "./modules/panos/r/panos_service_group"

  # name - (required) is a type of string
  name = null
  # services - (required) is a type of list of string
  services = []
  # tags - (optional) is a type of set of string
  tags = []
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The service group's name"
  type        = string
}

variable "services" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional) - Administrative tags for the service group"
  type        = set(string)
  default     = null
}

variable "vsys" {
  description = "(optional) - The vsys to put this service group in"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_service_group" "this" {
  name     = var.name
  services = var.services
  tags     = var.tags
  vsys     = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_service_group.this.id
}

output "this" {
  value = panos_service_group.this
}
```

[top](#index)