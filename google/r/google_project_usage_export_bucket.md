# google_project_usage_export_bucket

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_project_usage_export_bucket" {
  source = "./modules/google/r/google_project_usage_export_bucket"

  # bucket_name - (required) is a type of string
  bucket_name = null
  # prefix - (optional) is a type of string
  prefix = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket_name" {
  description = "(required) - The bucket to store reports in."
  type        = string
}

variable "prefix" {
  description = "(optional) - A prefix for the reports, for instance, the project name."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The project to set the export bucket on. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_project_usage_export_bucket" "this" {
  bucket_name = var.bucket_name
  prefix      = var.prefix
  project     = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_project_usage_export_bucket.this.id
}

output "project" {
  description = "returns a string"
  value       = google_project_usage_export_bucket.this.project
}

output "this" {
  value = google_project_usage_export_bucket.this
}
```

[top](#index)