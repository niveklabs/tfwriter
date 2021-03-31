# fortios_fmg_object_adom_revision

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_fmg_object_adom_revision" {
  source = "./modules/fortios/r/fortios_fmg_object_adom_revision"

  # adom - (optional) is a type of string
  adom = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # locked - (optional) is a type of number
  locked = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "locked" {
  description = "(optional)"
  type        = number
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
resource "fortios_fmg_object_adom_revision" "this" {
  adom        = var.adom
  created_by  = var.created_by
  description = var.description
  locked      = var.locked
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_object_adom_revision.this.id
}

output "this" {
  value = fortios_fmg_object_adom_revision.this
}
```

[top](#index)