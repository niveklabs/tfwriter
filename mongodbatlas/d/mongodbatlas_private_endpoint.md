# mongodbatlas_private_endpoint

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
module "mongodbatlas_private_endpoint" {
  source = "./modules/mongodbatlas/d/mongodbatlas_private_endpoint"

  # private_link_id - (required) is a type of string
  private_link_id = null
  # project_id - (required) is a type of string
  project_id = null
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
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_private_endpoint" "this" {
  private_link_id = var.private_link_id
  project_id      = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "endpoint_service_name" {
  description = "returns a string"
  value       = data.mongodbatlas_private_endpoint.this.endpoint_service_name
}

output "error_message" {
  description = "returns a string"
  value       = data.mongodbatlas_private_endpoint.this.error_message
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_private_endpoint.this.id
}

output "interface_endpoints" {
  description = "returns a list of string"
  value       = data.mongodbatlas_private_endpoint.this.interface_endpoints
}

output "status" {
  description = "returns a string"
  value       = data.mongodbatlas_private_endpoint.this.status
}

output "this" {
  value = mongodbatlas_private_endpoint.this
}
```

[top](#index)