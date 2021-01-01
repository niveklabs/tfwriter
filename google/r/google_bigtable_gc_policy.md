# google_bigtable_gc_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_bigtable_gc_policy" {
  source = "./modules/google/r/google_bigtable_gc_policy"

  # column_family - (required) is a type of string
  column_family = null
  # instance_name - (required) is a type of string
  instance_name = null
  # mode - (optional) is a type of string
  mode = null
  # project - (optional) is a type of string
  project = null
  # table - (required) is a type of string
  table = null

  max_age = [{
    days = null
  }]

  max_version = [{
    number = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "column_family" {
  description = "(required) - The name of the column family."
  type        = string
}

variable "instance_name" {
  description = "(required) - The name of the Bigtable instance."
  type        = string
}

variable "mode" {
  description = "(optional) - If multiple policies are set, you should choose between UNION OR INTERSECTION."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "table" {
  description = "(required) - The name of the table."
  type        = string
}

variable "max_age" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      days = number
    }
  ))
  default = []
}

variable "max_version" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      number = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_bigtable_gc_policy" "this" {
  column_family = var.column_family
  instance_name = var.instance_name
  mode          = var.mode
  project       = var.project
  table         = var.table

  dynamic "max_age" {
    for_each = var.max_age
    content {
      days = max_age.value["days"]
    }
  }

  dynamic "max_version" {
    for_each = var.max_version
    content {
      number = max_version.value["number"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_bigtable_gc_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigtable_gc_policy.this.project
}

output "this" {
  value = google_bigtable_gc_policy.this
}
```

[top](#index)