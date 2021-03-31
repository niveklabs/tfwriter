# google_runtimeconfig_variable

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_runtimeconfig_variable" {
  source = "./modules/google-beta/d/google_runtimeconfig_variable"

  # name - (required) is a type of string
  name = null
  # parent - (required) is a type of string
  parent = null
  # project - (optional) is a type of string
  project = null
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
```

[top](#index)

### Datasource

```terraform
data "google_runtimeconfig_variable" "this" {
  name    = var.name
  parent  = var.parent
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_runtimeconfig_variable.this.id
}

output "text" {
  description = "returns a string"
  value       = data.google_runtimeconfig_variable.this.text
}

output "update_time" {
  description = "returns a string"
  value       = data.google_runtimeconfig_variable.this.update_time
}

output "value" {
  description = "returns a string"
  value       = data.google_runtimeconfig_variable.this.value
}

output "this" {
  value = google_runtimeconfig_variable.this
}
```

[top](#index)