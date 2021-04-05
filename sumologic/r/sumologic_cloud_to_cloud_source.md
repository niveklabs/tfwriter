# sumologic_cloud_to_cloud_source

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "sumologic_cloud_to_cloud_source" {
  source = "./modules/sumologic/r/sumologic_cloud_to_cloud_source"

  # collector_id - (required) is a type of number
  collector_id = null
  # config - (required) is a type of string
  config = null
  # schema_ref - (required) is a type of map of string
  schema_ref = {}
}
```

[top](#index)

### Variables

```terraform
variable "collector_id" {
  description = "(required)"
  type        = number
}

variable "config" {
  description = "(required)"
  type        = string
}

variable "schema_ref" {
  description = "(required)"
  type        = map(string)
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_cloud_to_cloud_source" "this" {
  collector_id = var.collector_id
  config       = var.config
  schema_ref   = var.schema_ref
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_cloud_to_cloud_source.this.id
}

output "this" {
  value = sumologic_cloud_to_cloud_source.this
}
```

[top](#index)