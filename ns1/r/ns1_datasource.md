# ns1_datasource

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_datasource" {
  source = "./modules/ns1/r/ns1_datasource"

  # config - (optional) is a type of map of string
  config = {}
  # name - (required) is a type of string
  name = null
  # sourcetype - (required) is a type of string
  sourcetype = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sourcetype" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ns1_datasource" "this" {
  config     = var.config
  name       = var.name
  sourcetype = var.sourcetype
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ns1_datasource.this.id
}

output "this" {
  value = ns1_datasource.this
}
```

[top](#index)