# circonus_worksheet

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "circonus_worksheet" {
  source = "./modules/circonus/r/circonus_worksheet"

  # description - (optional) is a type of string
  description = null
  # favourite - (optional) is a type of bool
  favourite = null
  # graphs - (optional) is a type of set of string
  graphs = []
  # notes - (optional) is a type of string
  notes = null
  # tags - (optional) is a type of set of string
  tags = []
  # title - (required) is a type of string
  title = null

  smart_queries = [{
    name  = null
    order = []
    query = null
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

variable "favourite" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "graphs" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "title" {
  description = "(required)"
  type        = string
}

variable "smart_queries" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      order = set(string)
      query = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "circonus_worksheet" "this" {
  description = var.description
  favourite   = var.favourite
  graphs      = var.graphs
  notes       = var.notes
  tags        = var.tags
  title       = var.title

  dynamic "smart_queries" {
    for_each = var.smart_queries
    content {
      name  = smart_queries.value["name"]
      order = smart_queries.value["order"]
      query = smart_queries.value["query"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = circonus_worksheet.this.id
}

output "this" {
  value = circonus_worksheet.this
}
```

[top](#index)