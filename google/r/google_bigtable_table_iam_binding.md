# google_bigtable_table_iam_binding

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigtable_table_iam_binding" {
  source = "./modules/google/r/google_bigtable_table_iam_binding"

  # instance - (required) is a type of string
  instance = null
  # members - (required) is a type of set of string
  members = []
  # project - (optional) is a type of string
  project = null
  # role - (required) is a type of string
  role = null
  # table - (required) is a type of string
  table = null

  condition = [{
    description = null
    expression  = null
    title       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance" {
  description = "(required)"
  type        = string
}

variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "table" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      expression  = string
      title       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_bigtable_table_iam_binding" "this" {
  instance = var.instance
  members  = var.members
  project  = var.project
  role     = var.role
  table    = var.table

  dynamic "condition" {
    for_each = var.condition
    content {
      description = condition.value["description"]
      expression  = condition.value["expression"]
      title       = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_bigtable_table_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_bigtable_table_iam_binding.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigtable_table_iam_binding.this.project
}

output "this" {
  value = google_bigtable_table_iam_binding.this
}
```

[top](#index)