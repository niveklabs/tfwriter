# boundary_host_set

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
module "boundary_host_set" {
  source = "./modules/boundary/r/boundary_host_set"

  # description - (optional) is a type of string
  description = null
  # host_catalog_id - (required) is a type of string
  host_catalog_id = null
  # host_ids - (optional) is a type of set of string
  host_ids = []
  # name - (optional) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The hostset description."
  type        = string
  default     = null
}

variable "host_catalog_id" {
  description = "(required) - The catalog for the hostset."
  type        = string
}

variable "host_ids" {
  description = "(optional) - The list of host IDs contained in this set."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - The hostset name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_host_set" "this" {
  # description - (optional) is a type of string
  description = var.description
  # host_catalog_id - (required) is a type of string
  host_catalog_id = var.host_catalog_id
  # host_ids - (optional) is a type of set of string
  host_ids = var.host_ids
  # name - (optional) is a type of string
  name = var.name
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_host_set.this.id
}

output "this" {
  value = boundary_host_set.this
}
```

[top](#index)