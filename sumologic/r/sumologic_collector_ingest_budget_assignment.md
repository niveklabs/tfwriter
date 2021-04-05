# sumologic_collector_ingest_budget_assignment

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
module "sumologic_collector_ingest_budget_assignment" {
  source = "./modules/sumologic/r/sumologic_collector_ingest_budget_assignment"

  # collector_id - (required) is a type of string
  collector_id = null
  # ingest_budget_id - (required) is a type of string
  ingest_budget_id = null
}
```

[top](#index)

### Variables

```terraform
variable "collector_id" {
  description = "(required)"
  type        = string
}

variable "ingest_budget_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_collector_ingest_budget_assignment" "this" {
  collector_id     = var.collector_id
  ingest_budget_id = var.ingest_budget_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_collector_ingest_budget_assignment.this.id
}

output "this" {
  value = sumologic_collector_ingest_budget_assignment.this
}
```

[top](#index)