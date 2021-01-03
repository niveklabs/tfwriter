# google_runtimeconfig_config

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_runtimeconfig_config" {
  source = "./modules/google-beta/r/google_runtimeconfig_config"

  # description - (optional) is a type of string
  description = null
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
  description = "(optional) - The description to associate with the runtime config."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the runtime config."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_runtimeconfig_config" "this" {
  description = var.description
  name        = var.name
  project     = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_runtimeconfig_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_runtimeconfig_config.this.project
}

output "this" {
  value = google_runtimeconfig_config.this
}
```

[top](#index)