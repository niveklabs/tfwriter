# null_data_source

[back](../null.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    null = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "null_data_source" {
  source = "./modules/null/d/null_data_source"

  # has_computed_default - (optional) is a type of string
  has_computed_default = null
  # inputs - (optional) is a type of map of string
  inputs = {}
}
```

[top](#index)

### Variables

```terraform
variable "has_computed_default" {
  description = "(optional) - If set, its literal value will be stored and returned. If not, its value defaults to `\"default\"`. This argument exists primarily for testing and has little practical use."
  type        = string
  default     = null
}

variable "inputs" {
  description = "(optional) - A map of arbitrary strings that is copied into the `outputs` attribute, and accessible directly for interpolation."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "null_data_source" "this" {
  # has_computed_default - (optional) is a type of string
  has_computed_default = var.has_computed_default
  # inputs - (optional) is a type of map of string
  inputs = var.inputs
}
```

[top](#index)

### Outputs

```terraform
output "has_computed_default" {
  description = "returns a string"
  value       = data.null_data_source.this.has_computed_default
}

output "id" {
  description = "returns a string"
  value       = data.null_data_source.this.id
}

output "outputs" {
  description = "returns a map of string"
  value       = data.null_data_source.this.outputs
}

output "random" {
  description = "returns a string"
  value       = data.null_data_source.this.random
}

output "this" {
  value = null_data_source.this
}
```

[top](#index)