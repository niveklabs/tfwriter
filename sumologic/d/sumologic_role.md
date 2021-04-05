# sumologic_role

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
module "sumologic_role" {
  source = "./modules/sumologic/d/sumologic_role"

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
data "sumologic_role" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "capabilities" {
  description = "returns a list of string"
  value       = data.sumologic_role.this.capabilities
}

output "description" {
  description = "returns a string"
  value       = data.sumologic_role.this.description
}

output "filter_predicate" {
  description = "returns a string"
  value       = data.sumologic_role.this.filter_predicate
}

output "id" {
  description = "returns a string"
  value       = data.sumologic_role.this.id
}

output "name" {
  description = "returns a string"
  value       = data.sumologic_role.this.name
}

output "this" {
  value = sumologic_role.this
}
```

[top](#index)