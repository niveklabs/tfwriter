# google_cloud_run_service

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
module "google_cloud_run_service" {
  source = "./modules/google-beta/d/google_cloud_run_service"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required) - The location of the cloud run instance. eg us-central1"
  type        = string
}

variable "name" {
  description = "(required) - Name must be unique within a namespace, within a Cloud Run region.\nIs required when creating resources. Name is primarily intended\nfor creation idempotence and configuration definition. Cannot be updated.\nMore info: http://kubernetes.io/docs/user-guide/identifiers#names"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_cloud_run_service" "this" {
  location = var.location
  name     = var.name
  project  = var.project
}
```

[top](#index)

### Outputs

```terraform
output "autogenerate_revision_name" {
  description = "returns a bool"
  value       = data.google_cloud_run_service.this.autogenerate_revision_name
}

output "id" {
  description = "returns a string"
  value       = data.google_cloud_run_service.this.id
}

output "metadata" {
  description = "returns a list of object"
  value       = data.google_cloud_run_service.this.metadata
}

output "status" {
  description = "returns a list of object"
  value       = data.google_cloud_run_service.this.status
}

output "template" {
  description = "returns a list of object"
  value       = data.google_cloud_run_service.this.template
}

output "traffic" {
  description = "returns a list of object"
  value       = data.google_cloud_run_service.this.traffic
}

output "this" {
  value = google_cloud_run_service.this
}
```

[top](#index)