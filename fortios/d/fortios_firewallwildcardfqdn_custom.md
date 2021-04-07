# fortios_firewallwildcardfqdn_custom

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
module "fortios_firewallwildcardfqdn_custom" {
  source = "./modules/fortios/d/fortios_firewallwildcardfqdn_custom"

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
data "fortios_firewallwildcardfqdn_custom" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = data.fortios_firewallwildcardfqdn_custom.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewallwildcardfqdn_custom.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallwildcardfqdn_custom.this.id
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewallwildcardfqdn_custom.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewallwildcardfqdn_custom.this.visibility
}

output "wildcard_fqdn" {
  description = "returns a string"
  value       = data.fortios_firewallwildcardfqdn_custom.this.wildcard_fqdn
}

output "this" {
  value = fortios_firewallwildcardfqdn_custom.this
}
```

[top](#index)