# panos_panorama_application_group

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
module "panos_panorama_application_group" {
  source = "./modules/panos/r/panos_panorama_application_group"

  # applications - (optional) is a type of list of string
  applications = []
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "applications" {
  description = "(optional)"
  type        = list(string)
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
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_application_group" "this" {
  # applications - (optional) is a type of list of string
  applications = var.applications
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_application_group.this.id
}

output "this" {
  value = panos_panorama_application_group.this
}
```

[top](#index)