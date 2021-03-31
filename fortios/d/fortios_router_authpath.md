# fortios_router_authpath

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
module "fortios_router_authpath" {
  source = "./modules/fortios/d/fortios_router_authpath"

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
data "fortios_router_authpath" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "device" {
  description = "returns a string"
  value       = data.fortios_router_authpath.this.device
}

output "gateway" {
  description = "returns a string"
  value       = data.fortios_router_authpath.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_authpath.this.id
}

output "this" {
  value = fortios_router_authpath.this
}
```

[top](#index)