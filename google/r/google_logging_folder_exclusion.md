# google_logging_folder_exclusion

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
module "google_logging_folder_exclusion" {
  source = "./modules/google/r/google_logging_folder_exclusion"

  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # filter - (required) is a type of string
  filter = null
  # folder - (required) is a type of string
  folder = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
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

variable "folder" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required) - The name of the logging exclusion."
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "google_logging_folder_exclusion" "this" {
  description = var.description
  disabled    = var.disabled
  filter      = var.filter
  folder      = var.folder
  name        = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_logging_folder_exclusion.this.id
}

output "this" {
  value = google_logging_folder_exclusion.this
}
```

[top](#index)