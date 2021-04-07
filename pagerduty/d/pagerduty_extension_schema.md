# pagerduty_extension_schema

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_extension_schema" {
  source = "./modules/pagerduty/d/pagerduty_extension_schema"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_extension_schema" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.pagerduty_extension_schema.this.id
}

output "type" {
  description = "returns a string"
  value       = data.pagerduty_extension_schema.this.type
}

output "this" {
  value = pagerduty_extension_schema.this
}
```

[top](#index)