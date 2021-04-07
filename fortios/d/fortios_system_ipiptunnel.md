# fortios_system_ipiptunnel

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
module "fortios_system_ipiptunnel" {
  source = "./modules/fortios/d/fortios_system_ipiptunnel"

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
data "fortios_system_ipiptunnel" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_ipiptunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_ipiptunnel.this.interface
}

output "local_gw" {
  description = "returns a string"
  value       = data.fortios_system_ipiptunnel.this.local_gw
}

output "remote_gw" {
  description = "returns a string"
  value       = data.fortios_system_ipiptunnel.this.remote_gw
}

output "this" {
  value = fortios_system_ipiptunnel.this
}
```

[top](#index)