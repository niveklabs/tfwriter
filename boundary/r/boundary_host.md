# boundary_host

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
module "boundary_host" {
  source = "./modules/boundary/r/boundary_host"

  # address - (optional) is a type of string
  address = null
  # description - (optional) is a type of string
  description = null
  # host_catalog_id - (required) is a type of string
  host_catalog_id = null
  # name - (optional) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional) - The static address of the host resource as `<IP>` (note: port assignment occurs in the target resource definition, do not add :port here) or a domain name."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - The host description."
  type        = string
  default     = null
}

variable "host_catalog_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional) - The host name. Defaults to the resource name."
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
resource "boundary_host" "this" {
  # address - (optional) is a type of string
  address = var.address
  # description - (optional) is a type of string
  description = var.description
  # host_catalog_id - (required) is a type of string
  host_catalog_id = var.host_catalog_id
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
  value       = boundary_host.this.id
}

output "this" {
  value = boundary_host.this
}
```

[top](#index)