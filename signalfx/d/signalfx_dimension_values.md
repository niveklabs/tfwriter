# signalfx_dimension_values

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_dimension_values" {
  source = "./modules/signalfx/d/signalfx_dimension_values"

  # query - (required) is a type of string
  query = null
}
```

[top](#index)

### Variables

```terraform
variable "query" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "signalfx_dimension_values" "this" {
  # query - (required) is a type of string
  query = var.query
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.signalfx_dimension_values.this.id
}

output "values" {
  description = "returns a list of string"
  value       = data.signalfx_dimension_values.this.values
}

output "this" {
  value = signalfx_dimension_values.this
}
```

[top](#index)