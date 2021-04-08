# vra_blueprint_version

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
module "vra_blueprint_version" {
  source = "./modules/vra/d/vra_blueprint_version"

  # blueprint_id - (required) is a type of string
  blueprint_id = null
}
```

[top](#index)

### Variables

```terraform
variable "blueprint_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_blueprint_version" "this" {
  # blueprint_id - (required) is a type of string
  blueprint_id = var.blueprint_id
}
```

[top](#index)

### Outputs

```terraform
output "blueprint_description" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.blueprint_description
}

output "content" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.content
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.org_id
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.project_id
}

output "project_name" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.project_name
}

output "status" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.updated_at
}

output "updated_by" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.updated_by
}

output "valid" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.valid
}

output "version" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.version
}

output "version_change_log" {
  description = "returns a string"
  value       = data.vra_blueprint_version.this.version_change_log
}

output "this" {
  value = vra_blueprint_version.this
}
```

[top](#index)