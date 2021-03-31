# fortios_system_mobiletunnellist

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
module "fortios_system_mobiletunnellist" {
  source = "./modules/fortios/d/fortios_system_mobiletunnellist"

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
data "fortios_system_mobiletunnellist" "this" {
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_mobiletunnellist.this.id
}

output "namelist" {
  description = "returns a list of string"
  value       = data.fortios_system_mobiletunnellist.this.namelist
}

output "this" {
  value = fortios_system_mobiletunnellist.this
}
```

[top](#index)