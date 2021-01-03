# mongodbatlas_network_peering

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
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_network_peering" {
  source = "./modules/mongodbatlas/d/mongodbatlas_network_peering"

  # peering_id - (required) is a type of string
  peering_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "peering_id" {
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
data "mongodbatlas_network_peering" "this" {
  peering_id = var.peering_id
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "accepter_region_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.accepter_region_name
}

output "atlas_cidr_block" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.atlas_cidr_block
}

output "atlas_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.atlas_id
}

output "aws_account_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.aws_account_id
}

output "azure_directory_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.azure_directory_id
}

output "azure_subscription_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.azure_subscription_id
}

output "connection_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.connection_id
}

output "container_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.container_id
}

output "error_message" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.error_message
}

output "error_state" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.error_state
}

output "error_state_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.error_state_name
}

output "gcp_project_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.gcp_project_id
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.id
}

output "network_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.network_name
}

output "provider_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.provider_name
}

output "resource_group_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.resource_group_name
}

output "route_table_cidr_block" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.route_table_cidr_block
}

output "status" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.status
}

output "status_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.status_name
}

output "vnet_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.vnet_name
}

output "vpc_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peering.this.vpc_id
}

output "this" {
  value = mongodbatlas_network_peering.this
}
```

[top](#index)