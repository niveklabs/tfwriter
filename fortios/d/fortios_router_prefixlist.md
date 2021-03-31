# fortios_router_prefixlist

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
module "fortios_router_prefixlist" {
  source = "./modules/fortios/d/fortios_router_prefixlist"

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
data "fortios_router_prefixlist" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = data.fortios_router_prefixlist.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_prefixlist.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = data.fortios_router_prefixlist.this.rule
}

output "this" {
  value = fortios_router_prefixlist.this
}
```

[top](#index)