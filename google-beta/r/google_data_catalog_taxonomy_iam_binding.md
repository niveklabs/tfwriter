# google_data_catalog_taxonomy_iam_binding

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
module "google_data_catalog_taxonomy_iam_binding" {
  source = "./modules/google-beta/r/google_data_catalog_taxonomy_iam_binding"

  # members - (required) is a type of set of string
  members = []
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # role - (required) is a type of string
  role = null
  # taxonomy - (required) is a type of string
  taxonomy = null

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
variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "taxonomy" {
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
resource "google_data_catalog_taxonomy_iam_binding" "this" {
  # members - (required) is a type of set of string
  members = var.members
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # role - (required) is a type of string
  role = var.role
  # taxonomy - (required) is a type of string
  taxonomy = var.taxonomy

  dynamic "condition" {
    for_each = var.condition
    content {
      # description - (optional) is a type of string
      description = condition.value["description"]
      # expression - (required) is a type of string
      expression = condition.value["expression"]
      # title - (required) is a type of string
      title = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_binding.this.id
}

output "project" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_binding.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_binding.this.region
}

output "this" {
  value = google_data_catalog_taxonomy_iam_binding.this
}
```

[top](#index)