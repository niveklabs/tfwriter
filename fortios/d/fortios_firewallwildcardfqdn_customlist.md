# fortios_firewallwildcardfqdn_customlist

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
module "fortios_firewallwildcardfqdn_customlist" {
  source = "./modules/fortios/d/fortios_firewallwildcardfqdn_customlist"

  # filter - (optional) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fortios_firewallwildcardfqdn_customlist" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_firewallwildcardfqdn_customlist.this.id
}

output "namelist" {
  description = "returns a list of string"
  value       = data.fortios_firewallwildcardfqdn_customlist.this.namelist
}

output "this" {
  value = fortios_firewallwildcardfqdn_customlist.this
}
```

[top](#index)