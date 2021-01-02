# google_secret_manager_secret_version

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_secret_manager_secret_version" {
  source = "./modules/google/d/google_secret_manager_secret_version"

  # project - (optional) is a type of string
  project = null
  # secret - (required) is a type of string
  secret = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_secret_manager_secret_version" "this" {
  project = var.project
  secret  = var.secret
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.create_time
}

output "destroy_time" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.destroy_time
}

output "enabled" {
  description = "returns a bool"
  value       = data.google_secret_manager_secret_version.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.name
}

output "project" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.project
}

output "secret_data" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.secret_data
  sensitive   = true
}

output "version" {
  description = "returns a string"
  value       = data.google_secret_manager_secret_version.this.version
}

output "this" {
  value = google_secret_manager_secret_version.this
}
```

[top](#index)