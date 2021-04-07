# fortios_router_accesslist

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
module "fortios_router_accesslist" {
  source = "./modules/fortios/d/fortios_router_accesslist"

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
data "fortios_router_accesslist" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = data.fortios_router_accesslist.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_accesslist.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = data.fortios_router_accesslist.this.rule
}

output "this" {
  value = fortios_router_accesslist.this
}
```

[top](#index)