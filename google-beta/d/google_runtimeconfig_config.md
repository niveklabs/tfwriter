# google_runtimeconfig_config

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
module "google_runtimeconfig_config" {
  source = "./modules/google-beta/d/google_runtimeconfig_config"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
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

### Datasource

```terraform
data "google_runtimeconfig_config" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_runtimeconfig_config.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_runtimeconfig_config.this.id
}

output "this" {
  value = google_runtimeconfig_config.this
}
```

[top](#index)