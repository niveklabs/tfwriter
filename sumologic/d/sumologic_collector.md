# sumologic_collector

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_collector" {
  source = "./modules/sumologic/d/sumologic_collector"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "sumologic_collector" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = data.sumologic_collector.this.category
}

output "description" {
  description = "returns a string"
  value       = data.sumologic_collector.this.description
}

output "fields" {
  description = "returns a map of string"
  value       = data.sumologic_collector.this.fields
}

output "id" {
  description = "returns a number"
  value       = data.sumologic_collector.this.id
}

output "name" {
  description = "returns a string"
  value       = data.sumologic_collector.this.name
}

output "timezone" {
  description = "returns a string"
  value       = data.sumologic_collector.this.timezone
}

output "this" {
  value = sumologic_collector.this
}
```

[top](#index)