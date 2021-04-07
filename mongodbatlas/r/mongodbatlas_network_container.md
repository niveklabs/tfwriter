# mongodbatlas_network_container

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
module "mongodbatlas_network_container" {
  source = "./modules/mongodbatlas/r/mongodbatlas_network_container"

  # atlas_cidr_block - (required) is a type of string
  atlas_cidr_block = null
  # project_id - (required) is a type of string
  project_id = null
  # provider_name - (optional) is a type of string
  provider_name = null
  # region - (optional) is a type of string
  region = null
  # region_name - (optional) is a type of string
  region_name = null
}
```

[top](#index)

### Variables

```terraform
variable "atlas_cidr_block" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_network_container" "this" {
  # atlas_cidr_block - (required) is a type of string
  atlas_cidr_block = var.atlas_cidr_block
  # project_id - (required) is a type of string
  project_id = var.project_id
  # provider_name - (optional) is a type of string
  provider_name = var.provider_name
  # region - (optional) is a type of string
  region = var.region
  # region_name - (optional) is a type of string
  region_name = var.region_name
}
```

[top](#index)

### Outputs

```terraform
output "azure_subscription_id" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.azure_subscription_id
}

output "container_id" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.container_id
}

output "gcp_project_id" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.gcp_project_id
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.id
}

output "network_name" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.network_name
}

output "provisioned" {
  description = "returns a bool"
  value       = mongodbatlas_network_container.this.provisioned
}

output "region" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.region
}

output "region_name" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.region_name
}

output "vnet_name" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.vnet_name
}

output "vpc_id" {
  description = "returns a string"
  value       = mongodbatlas_network_container.this.vpc_id
}

output "this" {
  value = mongodbatlas_network_container.this
}
```

[top](#index)