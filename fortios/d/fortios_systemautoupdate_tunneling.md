# fortios_systemautoupdate_tunneling

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
module "fortios_systemautoupdate_tunneling" {
  source = "./modules/fortios/d/fortios_systemautoupdate_tunneling"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_systemautoupdate_tunneling" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_tunneling.this.address
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_tunneling.this.id
}

output "password" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_tunneling.this.password
  sensitive   = true
}

output "port" {
  description = "returns a number"
  value       = data.fortios_systemautoupdate_tunneling.this.port
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_tunneling.this.status
}

output "username" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_tunneling.this.username
}

output "this" {
  value = fortios_systemautoupdate_tunneling.this
}
```

[top](#index)