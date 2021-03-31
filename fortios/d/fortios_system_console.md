# fortios_system_console

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
module "fortios_system_console" {
  source = "./modules/fortios/d/fortios_system_console"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_console" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "baudrate" {
  description = "returns a string"
  value       = data.fortios_system_console.this.baudrate
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_console.this.id
}

output "login" {
  description = "returns a string"
  value       = data.fortios_system_console.this.login
}

output "mode" {
  description = "returns a string"
  value       = data.fortios_system_console.this.mode
}

output "output" {
  description = "returns a string"
  value       = data.fortios_system_console.this.output
}

output "this" {
  value = fortios_system_console.this
}
```

[top](#index)