# sumologic_http_source

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
module "sumologic_http_source" {
  source = "./modules/sumologic/d/sumologic_http_source"

  # collector_id - (optional) is a type of number
  collector_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "collector_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "sumologic_http_source" "this" {
  # collector_id - (optional) is a type of number
  collector_id = var.collector_id
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = data.sumologic_http_source.this.category
}

output "description" {
  description = "returns a string"
  value       = data.sumologic_http_source.this.description
}

output "id" {
  description = "returns a number"
  value       = data.sumologic_http_source.this.id
}

output "multiline" {
  description = "returns a bool"
  value       = data.sumologic_http_source.this.multiline
}

output "timezone" {
  description = "returns a string"
  value       = data.sumologic_http_source.this.timezone
}

output "url" {
  description = "returns a string"
  value       = data.sumologic_http_source.this.url
}

output "this" {
  value = sumologic_http_source.this
}
```

[top](#index)