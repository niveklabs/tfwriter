# fortios_system_dnsserver

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
module "fortios_system_dnsserver" {
  source = "./modules/fortios/d/fortios_system_dnsserver"

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
data "fortios_system_dnsserver" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "dnsfilter_profile" {
  description = "returns a string"
  value       = data.fortios_system_dnsserver.this.dnsfilter_profile
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_dnsserver.this.id
}

output "mode" {
  description = "returns a string"
  value       = data.fortios_system_dnsserver.this.mode
}

output "this" {
  value = fortios_system_dnsserver.this
}
```

[top](#index)