# fortios_router_communitylist

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
module "fortios_router_communitylist" {
  source = "./modules/fortios/d/fortios_router_communitylist"

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
data "fortios_router_communitylist" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_router_communitylist.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = data.fortios_router_communitylist.this.rule
}

output "type" {
  description = "returns a string"
  value       = data.fortios_router_communitylist.this.type
}

output "this" {
  value = fortios_router_communitylist.this
}
```

[top](#index)