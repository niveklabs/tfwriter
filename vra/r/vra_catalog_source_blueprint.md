# vra_catalog_source_blueprint

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vra_catalog_source_blueprint" {
  source = "./modules/vra/r/vra_catalog_source_blueprint"

  # config - (optional) is a type of map of string
  config = {}
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
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
resource "vra_catalog_source_blueprint" "this" {
  # config - (optional) is a type of map of string
  config = var.config
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "config" {
  description = "returns a map of string"
  value       = vra_catalog_source_blueprint.this.config
}

output "created_at" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.created_by
}

output "global" {
  description = "returns a bool"
  value       = vra_catalog_source_blueprint.this.global
}

output "id" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.id
}

output "items_found" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.items_found
}

output "items_imported" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.items_imported
}

output "last_import_completed_at" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.last_import_completed_at
}

output "last_import_errors" {
  description = "returns a list of string"
  value       = vra_catalog_source_blueprint.this.last_import_errors
}

output "last_import_started_at" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.last_import_started_at
}

output "last_updated_by" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.last_updated_by
}

output "type_id" {
  description = "returns a string"
  value       = vra_catalog_source_blueprint.this.type_id
}

output "this" {
  value = vra_catalog_source_blueprint.this
}
```

[top](#index)