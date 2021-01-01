# google_bigtable_table_iam_member

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_bigtable_table_iam_member" {
  source = "./modules/google/r/google_bigtable_table_iam_member"

  # instance - (required) is a type of string
  instance = null
  # member - (required) is a type of string
  member = null
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

```hcl
variable "instance" {
  description = "(required)"
  type        = string
}

variable "member" {
  description = "(required)"
  type        = string
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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

```hcl
resource "google_bigtable_table_iam_member" "this" {
  instance = var.instance
  member   = var.member
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

```hcl
output "etag" {
  description = "returns a string"
  value       = google_bigtable_table_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_bigtable_table_iam_member.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigtable_table_iam_member.this.project
}

output "this" {
  value = google_bigtable_table_iam_member.this
}
```

[top](#index)