# google_firebase_web_app

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_firebase_web_app" {
  source = "./modules/google-beta/d/google_firebase_web_app"

  # app_id - (required) is a type of string
  app_id = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required) - Immutable. The globally unique, Firebase-assigned identifier of the App.\n\nThis identifier should be treated as an opaque token, as the data format is not specified."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_firebase_web_app" "this" {
  app_id = var.app_id
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_firebase_web_app.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_firebase_web_app.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_firebase_web_app.this.name
}

output "project" {
  description = "returns a string"
  value       = data.google_firebase_web_app.this.project
}

output "this" {
  value = google_firebase_web_app.this
}
```

[top](#index)