# vra_content_source

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
module "vra_content_source" {
  source = "./modules/vra/r/vra_content_source"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # sync_enabled - (required) is a type of bool
  sync_enabled = null
  # type_id - (required) is a type of string
  type_id = null

  config = [{
    branch         = null
    content_type   = null
    integration_id = null
    path           = null
    project_name   = null
    repository     = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "sync_enabled" {
  description = "(required)"
  type        = bool
}

variable "type_id" {
  description = "(required)"
  type        = string
}

variable "config" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      branch         = string
      content_type   = string
      integration_id = string
      path           = string
      project_name   = string
      repository     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vra_content_source" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # sync_enabled - (required) is a type of bool
  sync_enabled = var.sync_enabled
  # type_id - (required) is a type of string
  type_id = var.type_id

  dynamic "config" {
    for_each = var.config
    content {
      # branch - (optional) is a type of string
      branch = config.value["branch"]
      # content_type - (optional) is a type of string
      content_type = config.value["content_type"]
      # integration_id - (required) is a type of string
      integration_id = config.value["integration_id"]
      # path - (required) is a type of string
      path = config.value["path"]
      # project_name - (required) is a type of string
      project_name = config.value["project_name"]
      # repository - (optional) is a type of string
      repository = config.value["repository"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_content_source.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = vra_content_source.this.created_by
}

output "id" {
  description = "returns a string"
  value       = vra_content_source.this.id
}

output "last_updated_at" {
  description = "returns a string"
  value       = vra_content_source.this.last_updated_at
}

output "last_updated_by" {
  description = "returns a string"
  value       = vra_content_source.this.last_updated_by
}

output "org_id" {
  description = "returns a string"
  value       = vra_content_source.this.org_id
}

output "this" {
  value = vra_content_source.this
}
```

[top](#index)