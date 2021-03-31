# fortios_router_multicastflow

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
module "fortios_router_multicastflow" {
  source = "./modules/fortios/d/fortios_router_multicastflow"

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
data "fortios_router_multicastflow" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = data.fortios_router_multicastflow.this.comments
}

output "flows" {
  description = "returns a list of object"
  value       = data.fortios_router_multicastflow.this.flows
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_multicastflow.this.id
}

output "this" {
  value = fortios_router_multicastflow.this
}
```

[top](#index)