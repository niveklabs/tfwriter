# fortios_router_aspathlist

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
module "fortios_router_aspathlist" {
  source = "./modules/fortios/d/fortios_router_aspathlist"

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
data "fortios_router_aspathlist" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_router_aspathlist.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = data.fortios_router_aspathlist.this.rule
}

output "this" {
  value = fortios_router_aspathlist.this
}
```

[top](#index)