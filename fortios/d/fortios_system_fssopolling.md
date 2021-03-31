# fortios_system_fssopolling

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
module "fortios_system_fssopolling" {
  source = "./modules/fortios/d/fortios_system_fssopolling"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_fssopolling" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "auth_password" {
  description = "returns a string"
  value       = data.fortios_system_fssopolling.this.auth_password
  sensitive   = true
}

output "authentication" {
  description = "returns a string"
  value       = data.fortios_system_fssopolling.this.authentication
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_fssopolling.this.id
}

output "listening_port" {
  description = "returns a number"
  value       = data.fortios_system_fssopolling.this.listening_port
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_fssopolling.this.status
}

output "this" {
  value = fortios_system_fssopolling.this
}
```

[top](#index)