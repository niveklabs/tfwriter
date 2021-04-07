# datadog_dashboard_list

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
module "datadog_dashboard_list" {
  source = "./modules/datadog/d/datadog_dashboard_list"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - A dashboard list name to limit the search."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "datadog_dashboard_list" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.datadog_dashboard_list.this.id
}

output "this" {
  value = datadog_dashboard_list.this
}
```

[top](#index)