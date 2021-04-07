# fortios_json_generic_api

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_json_generic_api"

  # path - (required) is a type of string
  path = null
  # specialparams - (optional) is a type of string
  specialparams = null
}
```

[top](#index)

### Variables

```terraform
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

### Datasource

```terraform
data "fortios_json_generic_api" "this" {
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
  value       = data.fortios_json_generic_api.this.id
}

output "response" {
  description = "returns a string"
  value       = data.fortios_json_generic_api.this.response
}

output "this" {
  value = fortios_json_generic_api.this
}
```

[top](#index)