# vra_catalog_item

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_catalog_item" {
  source = "./modules/vra/d/vra_catalog_item"

  # expand_projects - (optional) is a type of bool
  expand_projects = null
  # expand_versions - (optional) is a type of bool
  expand_versions = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "expand_projects" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "expand_versions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vra_catalog_item" "this" {
  # expand_projects - (optional) is a type of bool
  expand_projects = var.expand_projects
  # expand_versions - (optional) is a type of bool
  expand_versions = var.expand_versions
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.id
}

output "last_updated_at" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.last_updated_at
}

output "last_updated_by" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.last_updated_by
}

output "name" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.name
}

output "project_ids" {
  description = "returns a list of string"
  value       = data.vra_catalog_item.this.project_ids
}

output "projects" {
  description = "returns a set of object"
  value       = data.vra_catalog_item.this.projects
}

output "schema" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.schema
}

output "source_id" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.source_id
}

output "source_name" {
  description = "returns a string"
  value       = data.vra_catalog_item.this.source_name
}

output "type" {
  description = "returns a set of object"
  value       = data.vra_catalog_item.this.type
}

output "versions" {
  description = "returns a set of object"
  value       = data.vra_catalog_item.this.versions
}

output "this" {
  value = vra_catalog_item.this
}
```

[top](#index)