# mongodbatlas_private_endpoint_interface_link

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
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_private_endpoint_interface_link" {
  source = "./modules/mongodbatlas/r/mongodbatlas_private_endpoint_interface_link"

  # interface_endpoint_id - (required) is a type of string
  interface_endpoint_id = null
  # private_link_id - (required) is a type of string
  private_link_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "interface_endpoint_id" {
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
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_private_endpoint_interface_link" "this" {
  interface_endpoint_id = var.interface_endpoint_id
  private_link_id       = var.private_link_id
  project_id            = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "connection_status" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint_interface_link.this.connection_status
}

output "delete_requested" {
  description = "returns a bool"
  value       = mongodbatlas_private_endpoint_interface_link.this.delete_requested
}

output "error_message" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint_interface_link.this.error_message
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_private_endpoint_interface_link.this.id
}

output "this" {
  value = mongodbatlas_private_endpoint_interface_link.this
}
```

[top](#index)