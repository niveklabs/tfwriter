# boundary_target

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
    boundary = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "boundary_target" {
  source = "./modules/boundary/r/boundary_target"

  # default_port - (optional) is a type of number
  default_port = null
  # description - (optional) is a type of string
  description = null
  # host_set_ids - (optional) is a type of set of string
  host_set_ids = []
  # name - (optional) is a type of string
  name = null
  # scope_id - (required) is a type of string
  scope_id = null
  # session_connection_limit - (optional) is a type of number
  session_connection_limit = null
  # session_max_seconds - (optional) is a type of number
  session_max_seconds = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "default_port" {
  description = "(optional) - The default port for this target."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The target description."
  type        = string
  default     = null
}

variable "host_set_ids" {
  description = "(optional) - A list of host set ID's."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - The target name. Defaults to the resource name."
  type        = string
  default     = null
}

variable "scope_id" {
  description = "(required) - The scope ID in which the resource is created. Defaults to the provider's `default_scope` if unset."
  type        = string
}

variable "session_connection_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_max_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - The target resource type."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "boundary_target" "this" {
  default_port             = var.default_port
  description              = var.description
  host_set_ids             = var.host_set_ids
  name                     = var.name
  scope_id                 = var.scope_id
  session_connection_limit = var.session_connection_limit
  session_max_seconds      = var.session_max_seconds
  type                     = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = boundary_target.this.id
}

output "session_connection_limit" {
  description = "returns a number"
  value       = boundary_target.this.session_connection_limit
}

output "session_max_seconds" {
  description = "returns a number"
  value       = boundary_target.this.session_max_seconds
}

output "this" {
  value = boundary_target.this
}
```

[top](#index)