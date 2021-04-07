# fortios_firewallservice_category

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
module "fortios_firewallservice_category" {
  source = "./modules/fortios/d/fortios_firewallservice_category"

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
data "fortios_firewallservice_category" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = data.fortios_firewallservice_category.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallservice_category.this.id
}

output "this" {
  value = fortios_firewallservice_category.this
}
```

[top](#index)