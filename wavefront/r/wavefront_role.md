# wavefront_role

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_role" {
  source = "./modules/wavefront/r/wavefront_role"

  # assignees - (optional) is a type of set of string
  assignees = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # permissions - (optional) is a type of set of string
  permissions = []
}
```

[top](#index)

### Variables

```terraform
variable "assignees" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_role" "this" {
  # assignees - (optional) is a type of set of string
  assignees = var.assignees
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # permissions - (optional) is a type of set of string
  permissions = var.permissions
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_role.this.id
}

output "this" {
  value = wavefront_role.this
}
```

[top](#index)