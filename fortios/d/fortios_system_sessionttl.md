# fortios_system_sessionttl

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
module "fortios_system_sessionttl" {
  source = "./modules/fortios/d/fortios_system_sessionttl"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_sessionttl" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a string"
  value       = data.fortios_system_sessionttl.this.default
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_sessionttl.this.id
}

output "port" {
  description = "returns a list of object"
  value       = data.fortios_system_sessionttl.this.port
}

output "this" {
  value = fortios_system_sessionttl.this
}
```

[top](#index)