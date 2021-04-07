# google_monitoring_istio_canonical_service

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
module "google_monitoring_istio_canonical_service" {
  source = "./modules/google-beta/d/google_monitoring_istio_canonical_service"

  # canonical_service - (required) is a type of string
  canonical_service = null
  # canonical_service_namespace - (required) is a type of string
  canonical_service_namespace = null
  # mesh_uid - (required) is a type of string
  mesh_uid = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "canonical_service" {
  description = "(required) - The name of the canonical service underlying this service.. \n                        Corresponds to the destination_service_name metric label in Istio metrics."
  type        = string
}

variable "canonical_service_namespace" {
  description = "(required) - The namespace of the canonical service underlying this service.\n                        Corresponds to the destination_service_namespace metric label in Istio metrics."
  type        = string
}

variable "mesh_uid" {
  description = "(required) - Identifier for the Istio mesh in which this canonical service is defined.\n                        Corresponds to the meshUid metric label in Istio metrics."
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
data "google_monitoring_istio_canonical_service" "this" {
  # canonical_service - (required) is a type of string
  canonical_service = var.canonical_service
  # canonical_service_namespace - (required) is a type of string
  canonical_service_namespace = var.canonical_service_namespace
  # mesh_uid - (required) is a type of string
  mesh_uid = var.mesh_uid
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_monitoring_istio_canonical_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_monitoring_istio_canonical_service.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_monitoring_istio_canonical_service.this.name
}

output "service_id" {
  description = "returns a string"
  value       = data.google_monitoring_istio_canonical_service.this.service_id
}

output "telemetry" {
  description = "returns a list of object"
  value       = data.google_monitoring_istio_canonical_service.this.telemetry
}

output "this" {
  value = google_monitoring_istio_canonical_service.this
}
```

[top](#index)