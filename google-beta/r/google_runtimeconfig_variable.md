# google_runtimeconfig_variable

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
module "google_runtimeconfig_variable" {
  source = "./modules/google-beta/r/google_runtimeconfig_variable"

  # name - (required) is a type of string
  name = null
  # parent - (required) is a type of string
  parent = null
  # project - (optional) is a type of string
  project = null
  # text - (optional) is a type of string
  text = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the variable to manage. Note that variable names can be hierarchical using slashes (e.g. \"prod-variables/hostname\")."
  type        = string
}

variable "parent" {
  description = "(required) - The name of the RuntimeConfig resource containing this variable."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "text" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_runtimeconfig_variable" "this" {
  # name - (required) is a type of string
  name = var.name
  # parent - (required) is a type of string
  parent = var.parent
  # project - (optional) is a type of string
  project = var.project
  # text - (optional) is a type of string
  text = var.text
  # value - (optional) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_runtimeconfig_variable.this.id
}

output "project" {
  description = "returns a string"
  value       = google_runtimeconfig_variable.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_runtimeconfig_variable.this.update_time
}

output "this" {
  value = google_runtimeconfig_variable.this
}
```

[top](#index)