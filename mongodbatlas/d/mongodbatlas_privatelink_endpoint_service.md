# mongodbatlas_privatelink_endpoint_service

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
module "mongodbatlas_privatelink_endpoint_service" {
  source = "./modules/mongodbatlas/d/mongodbatlas_privatelink_endpoint_service"

  # endpoint_service_id - (required) is a type of string
  endpoint_service_id = null
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
variable "endpoint_service_id" {
  description = "(required)"
  type        = string
}

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
data "mongodbatlas_privatelink_endpoint_service" "this" {
  endpoint_service_id = var.endpoint_service_id
  private_link_id     = var.private_link_id
  project_id          = var.project_id
  provider_name       = var.provider_name
}
```

[top](#index)

### Outputs

```terraform
output "aws_connection_status" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.aws_connection_status
}

output "azure_status" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.azure_status
}

output "delete_requested" {
  description = "returns a bool"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.delete_requested
}

output "error_message" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.error_message
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.id
}

output "interface_endpoint_id" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.interface_endpoint_id
}

output "private_endpoint_connection_name" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.private_endpoint_connection_name
}

output "private_endpoint_ip_address" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.private_endpoint_ip_address
}

output "private_endpoint_resource_id" {
  description = "returns a string"
  value       = data.mongodbatlas_privatelink_endpoint_service.this.private_endpoint_resource_id
}

output "this" {
  value = mongodbatlas_privatelink_endpoint_service.this
}
```

[top](#index)