# vra_blueprint

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
module "vra_blueprint" {
  source = "./modules/vra/d/vra_blueprint"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vra_blueprint" "this" {
  # name - (optional) is a type of string
  name = var.name
  # project_id - (optional) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = data.vra_blueprint.this.content
}

output "content_source_id" {
  description = "returns a string"
  value       = data.vra_blueprint.this.content_source_id
}

output "content_source_path" {
  description = "returns a string"
  value       = data.vra_blueprint.this.content_source_path
}

output "content_source_sync_at" {
  description = "returns a string"
  value       = data.vra_blueprint.this.content_source_sync_at
}

output "content_source_sync_messages" {
  description = "returns a list of string"
  value       = data.vra_blueprint.this.content_source_sync_messages
}

output "content_source_sync_status" {
  description = "returns a string"
  value       = data.vra_blueprint.this.content_source_sync_status
}

output "content_source_type" {
  description = "returns a string"
  value       = data.vra_blueprint.this.content_source_type
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_blueprint.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = data.vra_blueprint.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.vra_blueprint.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_blueprint.this.id
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_blueprint.this.org_id
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_blueprint.this.project_id
}

output "project_name" {
  description = "returns a string"
  value       = data.vra_blueprint.this.project_name
}

output "request_scope_org" {
  description = "returns a bool"
  value       = data.vra_blueprint.this.request_scope_org
}

output "self_link" {
  description = "returns a string"
  value       = data.vra_blueprint.this.self_link
}

output "status" {
  description = "returns a string"
  value       = data.vra_blueprint.this.status
}

output "total_released_versions" {
  description = "returns a number"
  value       = data.vra_blueprint.this.total_released_versions
}

output "total_versions" {
  description = "returns a number"
  value       = data.vra_blueprint.this.total_versions
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_blueprint.this.updated_at
}

output "updated_by" {
  description = "returns a string"
  value       = data.vra_blueprint.this.updated_by
}

output "valid" {
  description = "returns a bool"
  value       = data.vra_blueprint.this.valid
}

output "validation_messages" {
  description = "returns a set of object"
  value       = data.vra_blueprint.this.validation_messages
}

output "this" {
  value = vra_blueprint.this
}
```

[top](#index)