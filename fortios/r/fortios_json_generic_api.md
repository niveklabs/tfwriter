# fortios_json_generic_api

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
module "fortios_json_generic_api" {
  source = "./modules/fortios/r/fortios_json_generic_api"

  # force_recreate - (optional) is a type of string
  force_recreate = null
  # json - (optional) is a type of string
  json = null
  # method - (required) is a type of string
  method = null
  # path - (required) is a type of string
  path = null
  # specialparams - (optional) is a type of string
  specialparams = null
}
```

[top](#index)

### Variables

```terraform
variable "force_recreate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "method" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "specialparams" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_json_generic_api" "this" {
  # force_recreate - (optional) is a type of string
  force_recreate = var.force_recreate
  # json - (optional) is a type of string
  json = var.json
  # method - (required) is a type of string
  method = var.method
  # path - (required) is a type of string
  path = var.path
  # specialparams - (optional) is a type of string
  specialparams = var.specialparams
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_json_generic_api.this.id
}

output "response" {
  description = "returns a string"
  value       = fortios_json_generic_api.this.response
}

output "this" {
  value = fortios_json_generic_api.this
}
```

[top](#index)