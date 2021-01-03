# gridscale_marketplace_application

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_marketplace_application" {
  source = "./modules/gridscale/d/gridscale_marketplace_application"

  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_marketplace_application" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.category
}

output "change_time" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.create_time
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.id
}

output "is_application_owner" {
  description = "returns a bool"
  value       = data.gridscale_marketplace_application.this.is_application_owner
}

output "is_publish_global" {
  description = "returns a bool"
  value       = data.gridscale_marketplace_application.this.is_publish_global
}

output "is_publish_global_requested" {
  description = "returns a bool"
  value       = data.gridscale_marketplace_application.this.is_publish_global_requested
}

output "is_publish_requested" {
  description = "returns a bool"
  value       = data.gridscale_marketplace_application.this.is_publish_requested
}

output "is_published" {
  description = "returns a bool"
  value       = data.gridscale_marketplace_application.this.is_published
}

output "meta_advices" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_advices
}

output "meta_author" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_author
}

output "meta_components" {
  description = "returns a set of string"
  value       = data.gridscale_marketplace_application.this.meta_components
}

output "meta_features" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_features
}

output "meta_hints" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_hints
}

output "meta_icon" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_icon
}

output "meta_license" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_license
}

output "meta_os" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_os
}

output "meta_overview" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_overview
}

output "meta_terms_of_use" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.meta_terms_of_use
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.name
}

output "object_storage_path" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.object_storage_path
}

output "publish_global_requested_date" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.publish_global_requested_date
}

output "publish_requested_date" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.publish_requested_date
}

output "published_date" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.published_date
}

output "published_global_date" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.published_global_date
}

output "setup_cores" {
  description = "returns a number"
  value       = data.gridscale_marketplace_application.this.setup_cores
}

output "setup_memory" {
  description = "returns a number"
  value       = data.gridscale_marketplace_application.this.setup_memory
}

output "setup_storage_capacity" {
  description = "returns a number"
  value       = data.gridscale_marketplace_application.this.setup_storage_capacity
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.status
}

output "type" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.type
}

output "unique_hash" {
  description = "returns a string"
  value       = data.gridscale_marketplace_application.this.unique_hash
}

output "this" {
  value = gridscale_marketplace_application.this
}
```

[top](#index)