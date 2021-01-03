# panos_panorama_service_group

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
module "panos_panorama_service_group" {
  source = "./modules/panos/r/panos_panorama_service_group"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # services - (required) is a type of list of string
  services = []
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional) - The device group to put this service group in"
  type        = string
  default     = null
}

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
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_service_group" "this" {
  device_group = var.device_group
  name         = var.name
  services     = var.services
  tags         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_service_group.this.id
}

output "this" {
  value = panos_panorama_service_group.this
}
```

[top](#index)