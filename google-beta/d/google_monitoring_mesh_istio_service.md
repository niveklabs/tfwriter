# google_monitoring_mesh_istio_service

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_monitoring_mesh_istio_service" {
  source = "./modules/google-beta/d/google_monitoring_mesh_istio_service"

  # mesh_uid - (required) is a type of string
  mesh_uid = null
  # project - (optional) is a type of string
  project = null
  # service_name - (required) is a type of string
  service_name = null
  # service_namespace - (required) is a type of string
  service_namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "mesh_uid" {
  description = "(required) - Identifier for the mesh in which this Istio service is defined.\n                        Corresponds to the meshUid metric label in Istio metrics."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required) - The name of the Istio service underlying this service. \n                        Corresponds to the destination_service_name metric label in Istio metrics."
  type        = string
}

variable "service_namespace" {
  description = "(required) - The namespace of the Istio service underlying this service.\n                        Corresponds to the destination_service_namespace metric label in Istio metrics."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_monitoring_mesh_istio_service" "this" {
  mesh_uid          = var.mesh_uid
  project           = var.project
  service_name      = var.service_name
  service_namespace = var.service_namespace
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_monitoring_mesh_istio_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_monitoring_mesh_istio_service.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_monitoring_mesh_istio_service.this.name
}

output "service_id" {
  description = "returns a string"
  value       = data.google_monitoring_mesh_istio_service.this.service_id
}

output "telemetry" {
  description = "returns a list of object"
  value       = data.google_monitoring_mesh_istio_service.this.telemetry
}

output "this" {
  value = google_monitoring_mesh_istio_service.this
}
```

[top](#index)