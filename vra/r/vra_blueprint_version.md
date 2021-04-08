# vra_blueprint_version

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
module "vra_blueprint_version" {
  source = "./modules/vra/r/vra_blueprint_version"

  # blueprint_id - (required) is a type of string
  blueprint_id = null
  # change_log - (optional) is a type of string
  change_log = null
  # description - (optional) is a type of string
  description = null
  # release - (optional) is a type of bool
  release = null
  # version - (required) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "blueprint_id" {
  description = "(required)"
  type        = string
}

variable "change_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "release" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vra_blueprint_version" "this" {
  # blueprint_id - (required) is a type of string
  blueprint_id = var.blueprint_id
  # change_log - (optional) is a type of string
  change_log = var.change_log
  # description - (optional) is a type of string
  description = var.description
  # release - (optional) is a type of bool
  release = var.release
  # version - (required) is a type of string
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "blueprint_description" {
  description = "returns a string"
  value       = vra_blueprint_version.this.blueprint_description
}

output "content" {
  description = "returns a string"
  value       = vra_blueprint_version.this.content
}

output "created_at" {
  description = "returns a string"
  value       = vra_blueprint_version.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = vra_blueprint_version.this.created_by
}

output "id" {
  description = "returns a string"
  value       = vra_blueprint_version.this.id
}

output "name" {
  description = "returns a string"
  value       = vra_blueprint_version.this.name
}

output "org_id" {
  description = "returns a string"
  value       = vra_blueprint_version.this.org_id
}

output "project_id" {
  description = "returns a string"
  value       = vra_blueprint_version.this.project_id
}

output "project_name" {
  description = "returns a string"
  value       = vra_blueprint_version.this.project_name
}

output "status" {
  description = "returns a string"
  value       = vra_blueprint_version.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = vra_blueprint_version.this.updated_at
}

output "updated_by" {
  description = "returns a string"
  value       = vra_blueprint_version.this.updated_by
}

output "valid" {
  description = "returns a string"
  value       = vra_blueprint_version.this.valid
}

output "this" {
  value = vra_blueprint_version.this
}
```

[top](#index)