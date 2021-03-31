# mongodbatlas_privatelink_endpoint

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "mongodbatlas_privatelink_endpoint" {
  source = "./modules/mongodbatlas/d/mongodbatlas_privatelink_endpoint"

  # private_link_id - (required) is a type of string
  private_link_id = null
  # project_id - (required) is a type of string
  project_id = null
  # provider_name - (required) is a type of string
  provider_name = null
}
```

[top](#index)

### Variables

```terraform
variable "private_link_id" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_privatelink_endpoint" "this" {
  private_link_id = var.private_link_id
  project_id      = var.project_id
  provider_name   = var.provider_name
}
```

[top](#index)

### Outputs

```terraform
output "endpoint_service_name" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint.this.endpoint_service_name
}

output "error_message" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint.this.error_message
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint.this.id
}

output "interface_endpoints" {
  description = "returns a list of string"
  value       = data.mongodbatlas_privatelink_endpoint.this.interface_endpoints
}

output "private_endpoints" {
  description = "returns a list of string"
  value       = data.mongodbatlas_privatelink_endpoint.this.private_endpoints
}

output "private_link_service_name" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint.this.private_link_service_name
}

output "private_link_service_resource_id" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint.this.private_link_service_resource_id
}

output "status" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint.this.status
}

output "this" {
  value = mongodbatlas_privatelink_endpoint.this
}
```

[top](#index)