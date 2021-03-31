# google_firebase_web_app_config

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
module "google_firebase_web_app_config" {
  source = "./modules/google-beta/d/google_firebase_web_app_config"

  # project - (optional) is a type of string
  project = null
  # web_app_id - (required) is a type of string
  web_app_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project" {
  description = "(optional) - The project id of the Firebase web App."
  type        = string
  default     = null
}

variable "web_app_id" {
  description = "(required) - The id of the Firebase web App."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_firebase_web_app_config" "this" {
  project    = var.project
  web_app_id = var.web_app_id
}
```

[top](#index)

### Outputs

```terraform
output "api_key" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.api_key
}

output "auth_domain" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.auth_domain
}

output "database_url" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.database_url
}

output "id" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.id
}

output "location_id" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.location_id
}

output "measurement_id" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.measurement_id
}

output "messaging_sender_id" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.messaging_sender_id
}

output "storage_bucket" {
  description = "returns a string"
  value       = data.google_firebase_web_app_config.this.storage_bucket
}

output "this" {
  value = google_firebase_web_app_config.this
}
```

[top](#index)