# mongodbatlas_network_peering

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
module "mongodbatlas_network_peering" {
  source = "./modules/mongodbatlas/r/mongodbatlas_network_peering"

  # accepter_region_name - (optional) is a type of string
  accepter_region_name = null
  # atlas_cidr_block - (optional) is a type of string
  atlas_cidr_block = null
  # atlas_gcp_project_id - (optional) is a type of string
  atlas_gcp_project_id = null
  # atlas_vpc_name - (optional) is a type of string
  atlas_vpc_name = null
  # aws_account_id - (optional) is a type of string
  aws_account_id = null
  # azure_directory_id - (optional) is a type of string
  azure_directory_id = null
  # azure_subscription_id - (optional) is a type of string
  azure_subscription_id = null
  # container_id - (required) is a type of string
  container_id = null
  # gcp_project_id - (optional) is a type of string
  gcp_project_id = null
  # network_name - (optional) is a type of string
  network_name = null
  # project_id - (required) is a type of string
  project_id = null
  # provider_name - (required) is a type of string
  provider_name = null
  # resource_group_name - (optional) is a type of string
  resource_group_name = null
  # route_table_cidr_block - (optional) is a type of string
  route_table_cidr_block = null
  # vnet_name - (optional) is a type of string
  vnet_name = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "accepter_region_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "atlas_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "atlas_gcp_project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "atlas_vpc_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_directory_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_subscription_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "container_id" {
  description = "(required)"
  type        = string
}

variable "gcp_project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vnet_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_network_peering" "this" {
  # accepter_region_name - (optional) is a type of string
  accepter_region_name = var.accepter_region_name
  # atlas_cidr_block - (optional) is a type of string
  atlas_cidr_block = var.atlas_cidr_block
  # atlas_gcp_project_id - (optional) is a type of string
  atlas_gcp_project_id = var.atlas_gcp_project_id
  # atlas_vpc_name - (optional) is a type of string
  atlas_vpc_name = var.atlas_vpc_name
  # aws_account_id - (optional) is a type of string
  aws_account_id = var.aws_account_id
  # azure_directory_id - (optional) is a type of string
  azure_directory_id = var.azure_directory_id
  # azure_subscription_id - (optional) is a type of string
  azure_subscription_id = var.azure_subscription_id
  # container_id - (required) is a type of string
  container_id = var.container_id
  # gcp_project_id - (optional) is a type of string
  gcp_project_id = var.gcp_project_id
  # network_name - (optional) is a type of string
  network_name = var.network_name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # provider_name - (required) is a type of string
  provider_name = var.provider_name
  # resource_group_name - (optional) is a type of string
  resource_group_name = var.resource_group_name
  # route_table_cidr_block - (optional) is a type of string
  route_table_cidr_block = var.route_table_cidr_block
  # vnet_name - (optional) is a type of string
  vnet_name = var.vnet_name
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "accepter_region_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.accepter_region_name
}

output "atlas_cidr_block" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.atlas_cidr_block
}

output "atlas_gcp_project_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.atlas_gcp_project_id
}

output "atlas_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.atlas_id
}

output "atlas_vpc_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.atlas_vpc_name
}

output "aws_account_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.aws_account_id
}

output "azure_directory_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.azure_directory_id
}

output "azure_subscription_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.azure_subscription_id
}

output "connection_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.connection_id
}

output "error_message" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.error_message
}

output "error_state" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.error_state
}

output "error_state_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.error_state_name
}

output "gcp_project_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.gcp_project_id
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.id
}

output "network_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.network_name
}

output "peer_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.peer_id
}

output "resource_group_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.resource_group_name
}

output "route_table_cidr_block" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.route_table_cidr_block
}

output "status" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.status
}

output "status_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.status_name
}

output "vnet_name" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.vnet_name
}

output "vpc_id" {
  description = "returns a string"
  value       = mongodbatlas_network_peering.this.vpc_id
}

output "this" {
  value = mongodbatlas_network_peering.this
}
```

[top](#index)