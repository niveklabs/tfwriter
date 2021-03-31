# fortios_router_bfd

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
module "fortios_router_bfd" {
  source = "./modules/fortios/d/fortios_router_bfd"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_bfd" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_router_bfd.this.id
}

output "neighbor" {
  description = "returns a list of object"
  value       = data.fortios_router_bfd.this.neighbor
}

output "this" {
  value = fortios_router_bfd.this
}
```

[top](#index)