# panos_device_group_parent

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
module "panos_device_group_parent" {
  source = "./modules/panos/d/panos_device_group_parent"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "panos_device_group_parent" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a map of string"
  value       = data.panos_device_group_parent.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.panos_device_group_parent.this.id
}

output "total" {
  description = "returns a number"
  value       = data.panos_device_group_parent.this.total
}

output "this" {
  value = panos_device_group_parent.this
}
```

[top](#index)