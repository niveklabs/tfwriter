# mongodbatlas_private_endpoint

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_private_endpoint" {
  source = "./modules/mongodbatlas/r/mongodbatlas_private_endpoint"

  # project_id - (required) is a type of string
  project_id = null
  # provider_name - (required) is a type of string
  provider_name = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_private_endpoint" "this" {
  project_id    = var.project_id
  provider_name = var.provider_name
  region        = var.region
}
```

[top](#index)

### Outputs

```terraform
output "endpoint_service_name" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint.this.endpoint_service_name
}

output "error_message" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint.this.error_message
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint.this.id
}

output "interface_endpoints" {
  description = "returns a list of string"
  value       = mongodbatlas_private_endpoint.this.interface_endpoints
}

output "private_link_id" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint.this.private_link_id
}

output "status" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint.this.status
}

output "this" {
  value = mongodbatlas_private_endpoint.this
}
```

[top](#index)