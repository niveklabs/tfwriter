# google_logging_project_exclusion

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
module "google_logging_project_exclusion" {
  source = "./modules/google-beta/r/google_logging_project_exclusion"

  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # filter - (required) is a type of string
  filter = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A human-readable description."
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional) - Whether this exclusion rule should be disabled or not. This defaults to false."
  type        = bool
  default     = null
}

variable "filter" {
  description = "(required) - The filter to apply when excluding logs. Only log entries that match the filter are excluded."
  type        = string
}

variable "name" {
  description = "(required) - The name of the logging exclusion."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_logging_project_exclusion" "this" {
  # description - (optional) is a type of string
  description = var.description
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # filter - (required) is a type of string
  filter = var.filter
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_logging_project_exclusion.this.id
}

output "project" {
  description = "returns a string"
  value       = google_logging_project_exclusion.this.project
}

output "this" {
  value = google_logging_project_exclusion.this
}
```

[top](#index)