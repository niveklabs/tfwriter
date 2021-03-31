# fortios_system_ftmpush

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
module "fortios_system_ftmpush" {
  source = "./modules/fortios/d/fortios_system_ftmpush"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_ftmpush" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_ftmpush.this.id
}

output "server_cert" {
  description = "returns a string"
  value       = data.fortios_system_ftmpush.this.server_cert
}

output "server_ip" {
  description = "returns a string"
  value       = data.fortios_system_ftmpush.this.server_ip
}

output "server_port" {
  description = "returns a number"
  value       = data.fortios_system_ftmpush.this.server_port
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_ftmpush.this.status
}

output "this" {
  value = fortios_system_ftmpush.this
}
```

[top](#index)