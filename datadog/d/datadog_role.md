# datadog_role

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
module "datadog_role" {
  source = "./modules/datadog/d/datadog_role"

  # filter - (required) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(required) - A string on which to filter the roles."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "datadog_role" "this" {
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.datadog_role.this.id
}

output "name" {
  description = "returns a string"
  value       = data.datadog_role.this.name
}

output "user_count" {
  description = "returns a number"
  value       = data.datadog_role.this.user_count
}

output "this" {
  value = datadog_role.this
}
```

[top](#index)