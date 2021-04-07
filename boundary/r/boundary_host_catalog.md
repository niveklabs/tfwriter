# boundary_host_catalog

[back](../boundary.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    boundary = ">= 1.0.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "boundary_host_catalog" {
  source = "./modules/boundary/r/boundary_host_catalog"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The host catalog description."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The host catalog name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "scope_id" {
  description = "(required) - The scope ID in which the resource is created."
  type        = string
}

variable "type" {
  description = "(required) - The host catalog type. Only `Static` (yes, title case) is supported."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_host_catalog" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # scope_id - (required) is a type of string
  scope_id = var.scope_id
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_host_catalog.this.id
}

output "this" {
  value = boundary_host_catalog.this
}
```

[top](#index)