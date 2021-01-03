# newrelic_workload

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_workload" {
  source = "./modules/newrelic/r/newrelic_workload"

  # account_id - (optional) is a type of number
  account_id = null
  # entity_guids - (optional) is a type of set of string
  entity_guids = []
  # name - (required) is a type of string
  name = null
  # scope_account_ids - (optional) is a type of set of number
  scope_account_ids = []

  entity_search_query = [{
    query = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The New Relic account ID where you want to create the workload."
  type        = number
  default     = null
}

variable "entity_guids" {
  description = "(optional) - A list of entity GUIDs manually assigned to this workload."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The workload's name."
  type        = string
}

variable "scope_account_ids" {
  description = "(optional) - A list of account IDs that will be used to get entities from."
  type        = set(number)
  default     = null
}

variable "entity_search_query" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      query = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_workload" "this" {
  account_id        = var.account_id
  entity_guids      = var.entity_guids
  name              = var.name
  scope_account_ids = var.scope_account_ids

  dynamic "entity_search_query" {
    for_each = var.entity_search_query
    content {
      query = entity_search_query.value["query"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_workload.this.account_id
}

output "composite_entity_search_query" {
  description = "returns a string"
  value       = newrelic_workload.this.composite_entity_search_query
}

output "entity_guids" {
  description = "returns a set of string"
  value       = newrelic_workload.this.entity_guids
}

output "guid" {
  description = "returns a string"
  value       = newrelic_workload.this.guid
}

output "id" {
  description = "returns a string"
  value       = newrelic_workload.this.id
}

output "permalink" {
  description = "returns a string"
  value       = newrelic_workload.this.permalink
}

output "scope_account_ids" {
  description = "returns a set of number"
  value       = newrelic_workload.this.scope_account_ids
}

output "workload_id" {
  description = "returns a number"
  value       = newrelic_workload.this.workload_id
}

output "this" {
  value = newrelic_workload.this
}
```

[top](#index)