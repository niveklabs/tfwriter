# panos_administrative_tag

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
module "panos_administrative_tag" {
  source = "./modules/panos/r/panos_administrative_tag"

  # color - (optional) is a type of string
  color = null
  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
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

variable "name" {
  description = "(required) - The administrative tag's name"
  type        = string
}

variable "vsys" {
  description = "(optional) - The vsys to put this administrative tag object in"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_administrative_tag" "this" {
  color   = var.color
  comment = var.comment
  name    = var.name
  vsys    = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_administrative_tag.this.id
}

output "this" {
  value = panos_administrative_tag.this
}
```

[top](#index)