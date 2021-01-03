# launchdarkly_segment

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_segment" {
  source = "./modules/launchdarkly/d/launchdarkly_segment"

  # description - (optional) is a type of string
  description = null
  # env_key - (required) is a type of string
  env_key = null
  # excluded - (optional) is a type of list of string
  excluded = []
  # included - (optional) is a type of list of string
  included = []
  # key - (required) is a type of string
  key = null
  # project_key - (required) is a type of string
  project_key = null
  # tags - (optional) is a type of set of string
  tags = []

  rules = [{
    bucket_by = null
    clauses = [{
      attribute = null
      negate    = null
      op        = null
      values    = []
    }]
    weight = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "env_key" {
  description = "(required)"
  type        = string
}

variable "excluded" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "included" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "project_key" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_by = string
      clauses = list(object(
        {
          attribute = string
          negate    = bool
          op        = string
          values    = list(string)
        }
      ))
      weight = number
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "launchdarkly_segment" "this" {
  description = var.description
  env_key     = var.env_key
  excluded    = var.excluded
  included    = var.included
  key         = var.key
  project_key = var.project_key
  tags        = var.tags

  dynamic "rules" {
    for_each = var.rules
    content {
      bucket_by = rules.value["bucket_by"]
      weight    = rules.value["weight"]

      dynamic "clauses" {
        for_each = rules.value.clauses
        content {
          attribute = clauses.value["attribute"]
          negate    = clauses.value["negate"]
          op        = clauses.value["op"]
          values    = clauses.value["values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.launchdarkly_segment.this.id
}

output "name" {
  description = "returns a string"
  value       = data.launchdarkly_segment.this.name
}

output "this" {
  value = launchdarkly_segment.this
}
```

[top](#index)