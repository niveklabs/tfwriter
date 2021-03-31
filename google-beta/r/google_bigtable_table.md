# google_bigtable_table

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigtable_table" {
  source = "./modules/google-beta/r/google_bigtable_table"

  # instance_name - (required) is a type of string
  instance_name = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # split_keys - (optional) is a type of list of string
  split_keys = []

  column_family = [{
    family = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_name" {
  description = "(required) - The name of the Bigtable instance."
  type        = string
}

variable "name" {
  description = "(required) - The name of the table."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "split_keys" {
  description = "(optional) - A list of predefined keys to split the table on. !> Warning: Modifying the split_keys of an existing table will cause Terraform to delete/recreate the entire google_bigtable_table resource."
  type        = list(string)
  default     = null
}

variable "column_family" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      family = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_bigtable_table" "this" {
  instance_name = var.instance_name
  name          = var.name
  project       = var.project
  split_keys    = var.split_keys

  dynamic "column_family" {
    for_each = var.column_family
    content {
      family = column_family.value["family"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_bigtable_table.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigtable_table.this.project
}

output "this" {
  value = google_bigtable_table.this
}
```

[top](#index)