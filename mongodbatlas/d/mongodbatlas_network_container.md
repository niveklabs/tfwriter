# mongodbatlas_network_container

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
module "mongodbatlas_network_container" {
  source = "./modules/mongodbatlas/d/mongodbatlas_network_container"

  # container_id - (required) is a type of string
  container_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "container_id" {
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
data "mongodbatlas_network_container" "this" {
  container_id = var.container_id
  project_id   = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "atlas_cidr_block" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.atlas_cidr_block
}

output "azure_subscription_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.azure_subscription_id
}

output "gcp_project_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.gcp_project_id
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.id
}

output "network_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.network_name
}

output "provider_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.provider_name
}

output "provisioned" {
  description = "returns a bool"
  value       = data.mongodbatlas_network_container.this.provisioned
}

output "region" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.region
}

output "region_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.region_name
}

output "vnet_name" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.vnet_name
}

output "vpc_id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_container.this.vpc_id
}

output "this" {
  value = mongodbatlas_network_container.this
}
```

[top](#index)