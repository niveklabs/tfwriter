# fortios_system_ipv6tunnel

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
module "fortios_system_ipv6tunnel" {
  source = "./modules/fortios/d/fortios_system_ipv6tunnel"

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
data "fortios_system_ipv6tunnel" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "destination" {
  description = "returns a string"
  value       = data.fortios_system_ipv6tunnel.this.destination
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_ipv6tunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_ipv6tunnel.this.interface
}

output "source" {
  description = "returns a string"
  value       = data.fortios_system_ipv6tunnel.this.source
}

output "this" {
  value = fortios_system_ipv6tunnel.this
}
```

[top](#index)