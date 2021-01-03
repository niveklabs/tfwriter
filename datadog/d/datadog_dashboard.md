# datadog_dashboard

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
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_dashboard" {
  source = "./modules/datadog/d/datadog_dashboard"

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
data "datadog_dashboard" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.datadog_dashboard.this.id
}

output "title" {
  description = "returns a string"
  value       = data.datadog_dashboard.this.title
}

output "url" {
  description = "returns a string"
  value       = data.datadog_dashboard.this.url
}

output "this" {
  value = datadog_dashboard.this
}
```

[top](#index)