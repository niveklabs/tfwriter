# panos_plugin

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_plugin" {
  source = "./modules/panos/d/panos_plugin"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "panos_plugin" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "details" {
  description = "returns a list of object"
  value       = data.panos_plugin.this.details
}

output "id" {
  description = "returns a string"
  value       = data.panos_plugin.this.id
}

output "installed" {
  description = "returns a list of string"
  value       = data.panos_plugin.this.installed
}

output "total" {
  description = "returns a number"
  value       = data.panos_plugin.this.total
}

output "this" {
  value = panos_plugin.this
}
```

[top](#index)