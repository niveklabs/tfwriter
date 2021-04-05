# google_bigtable_gc_policy

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigtable_gc_policy" {
  source = "./modules/google-beta/r/google_bigtable_gc_policy"

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
    days     = null
    duration = null
  }]

  max_version = [{
    number = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      days     = number
      duration = string
    }
  ))
  default = []
}

variable "max_version" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

```terraform
resource "google_bigtable_gc_policy" "this" {
  column_family = var.column_family
  instance_name = var.instance_name
  mode          = var.mode
  project       = var.project
  table         = var.table

  dynamic "max_age" {
    for_each = var.max_age
    content {
      days     = max_age.value["days"]
      duration = max_age.value["duration"]
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

```terraform
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