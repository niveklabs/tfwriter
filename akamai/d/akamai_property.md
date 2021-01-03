# akamai_property

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property" {
  source = "./modules/akamai/d/akamai_property"

  # name - (required) is a type of string
  name = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_property" "this" {
  name    = var.name
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_property.this.id
}

output "rules" {
  description = "returns a string"
  value       = data.akamai_property.this.rules
}

output "this" {
  value = akamai_property.this
}
```

[top](#index)