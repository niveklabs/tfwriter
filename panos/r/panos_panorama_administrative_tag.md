# panos_panorama_administrative_tag

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
module "panos_panorama_administrative_tag" {
  source = "./modules/panos/r/panos_panorama_administrative_tag"

  # color - (optional) is a type of string
  color = null
  # comment - (optional) is a type of string
  comment = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional) - The device group to put this administrative tag object in"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The administrative tag's name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_administrative_tag" "this" {
  color        = var.color
  comment      = var.comment
  device_group = var.device_group
  name         = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_administrative_tag.this.id
}

output "this" {
  value = panos_panorama_administrative_tag.this
}
```

[top](#index)