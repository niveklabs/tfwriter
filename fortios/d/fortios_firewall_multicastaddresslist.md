# fortios_firewall_multicastaddresslist

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
module "fortios_firewall_multicastaddresslist" {
  source = "./modules/fortios/d/fortios_firewall_multicastaddresslist"

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
data "fortios_firewall_multicastaddresslist" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddresslist.this.id
}

output "namelist" {
  description = "returns a list of string"
  value       = data.fortios_firewall_multicastaddresslist.this.namelist
}

output "this" {
  value = fortios_firewall_multicastaddresslist.this
}
```

[top](#index)