# vra_blueprint

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
module "vra_blueprint" {
  source = "./modules/vra/r/vra_blueprint"

  # content - (optional) is a type of string
  content = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # request_scope_org - (optional) is a type of bool
  request_scope_org = null
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(optional)"
  type        = string
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

variable "request_scope_org" {
  description = "(optional) - Flag to indicate blueprint can be requested from any project in org"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vra_blueprint" "this" {
  # content - (optional) is a type of string
  content = var.content
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # request_scope_org - (optional) is a type of bool
  request_scope_org = var.request_scope_org
}
```

[top](#index)

### Outputs

```terraform
output "content_source_id" {
  description = "returns a string"
  value       = vra_blueprint.this.content_source_id
}

output "content_source_path" {
  description = "returns a string"
  value       = vra_blueprint.this.content_source_path
}

output "content_source_sync_at" {
  description = "returns a string"
  value       = vra_blueprint.this.content_source_sync_at
}

output "content_source_sync_messages" {
  description = "returns a list of string"
  value       = vra_blueprint.this.content_source_sync_messages
}

output "content_source_sync_status" {
  description = "returns a string"
  value       = vra_blueprint.this.content_source_sync_status
}

output "content_source_type" {
  description = "returns a string"
  value       = vra_blueprint.this.content_source_type
}

output "created_at" {
  description = "returns a string"
  value       = vra_blueprint.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = vra_blueprint.this.created_by
}

output "description" {
  description = "returns a string"
  value       = vra_blueprint.this.description
}

output "id" {
  description = "returns a string"
  value       = vra_blueprint.this.id
}

output "org_id" {
  description = "returns a string"
  value       = vra_blueprint.this.org_id
}

output "project_name" {
  description = "returns a string"
  value       = vra_blueprint.this.project_name
}

output "request_scope_org" {
  description = "returns a bool"
  value       = vra_blueprint.this.request_scope_org
}

output "self_link" {
  description = "returns a string"
  value       = vra_blueprint.this.self_link
}

output "status" {
  description = "returns a string"
  value       = vra_blueprint.this.status
}

output "total_released_versions" {
  description = "returns a number"
  value       = vra_blueprint.this.total_released_versions
}

output "total_versions" {
  description = "returns a number"
  value       = vra_blueprint.this.total_versions
}

output "updated_at" {
  description = "returns a string"
  value       = vra_blueprint.this.updated_at
}

output "updated_by" {
  description = "returns a string"
  value       = vra_blueprint.this.updated_by
}

output "valid" {
  description = "returns a bool"
  value       = vra_blueprint.this.valid
}

output "validation_messages" {
  description = "returns a set of object"
  value       = vra_blueprint.this.validation_messages
}

output "this" {
  value = vra_blueprint.this
}
```

[top](#index)