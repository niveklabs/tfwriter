# circonus_collector

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.12.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_collector" {
  source = "./modules/circonus/d/circonus_collector"

  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "circonus_collector" "this" {
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "details" {
  description = "returns a list of object"
  value       = data.circonus_collector.this.details
}

output "id" {
  description = "returns a string"
  value       = data.circonus_collector.this.id
}

output "latitude" {
  description = "returns a string"
  value       = data.circonus_collector.this.latitude
}

output "longitude" {
  description = "returns a string"
  value       = data.circonus_collector.this.longitude
}

output "name" {
  description = "returns a string"
  value       = data.circonus_collector.this.name
}

output "type" {
  description = "returns a string"
  value       = data.circonus_collector.this.type
}

output "this" {
  value = circonus_collector.this
}
```

[top](#index)