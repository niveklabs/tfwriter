# fortios_firewallservice_group

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
module "fortios_firewallservice_group" {
  source = "./modules/fortios/d/fortios_firewallservice_group"

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
data "fortios_firewallservice_group" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = data.fortios_firewallservice_group.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewallservice_group.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallservice_group.this.id
}

output "member" {
  description = "returns a list of object"
  value       = data.fortios_firewallservice_group.this.member
}

output "proxy" {
  description = "returns a string"
  value       = data.fortios_firewallservice_group.this.proxy
}

output "this" {
  value = fortios_firewallservice_group.this
}
```

[top](#index)