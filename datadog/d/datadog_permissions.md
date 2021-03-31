# datadog_permissions

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_permissions" {
  source = "./modules/datadog/d/datadog_permissions"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "datadog_permissions" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.datadog_permissions.this.id
}

output "permissions" {
  description = "returns a map of string"
  value       = data.datadog_permissions.this.permissions
}

output "this" {
  value = datadog_permissions.this
}
```

[top](#index)