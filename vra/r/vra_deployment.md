# vra_deployment

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
module "vra_deployment" {
  source = "./modules/vra/r/vra_deployment"

  # blueprint_content - (optional) is a type of string
  blueprint_content = null
  # blueprint_id - (optional) is a type of string
  blueprint_id = null
  # blueprint_version - (optional) is a type of string
  blueprint_version = null
  # catalog_item_id - (optional) is a type of string
  catalog_item_id = null
  # catalog_item_version - (optional) is a type of string
  catalog_item_version = null
  # description - (optional) is a type of string
  description = null
  # expand_last_request - (optional) is a type of bool
  expand_last_request = null
  # expand_project - (optional) is a type of bool
  expand_project = null
  # expand_resources - (optional) is a type of bool
  expand_resources = null
  # inputs - (optional) is a type of map of string
  inputs = {}
  # lease_expire_at - (optional) is a type of string
  lease_expire_at = null
  # name - (required) is a type of string
  name = null
  # owner - (optional) is a type of string
  owner = null
  # project_id - (required) is a type of string
  project_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "blueprint_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "blueprint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "blueprint_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "catalog_item_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "catalog_item_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expand_last_request" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "expand_project" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "expand_resources" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "inputs" {
  description = "(optional) - Inputs provided by the user. For inputs including those with default values, refer to inputs_including_defaults."
  type        = map(string)
  default     = null
}

variable "lease_expire_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_deployment" "this" {
  # blueprint_content - (optional) is a type of string
  blueprint_content = var.blueprint_content
  # blueprint_id - (optional) is a type of string
  blueprint_id = var.blueprint_id
  # blueprint_version - (optional) is a type of string
  blueprint_version = var.blueprint_version
  # catalog_item_id - (optional) is a type of string
  catalog_item_id = var.catalog_item_id
  # catalog_item_version - (optional) is a type of string
  catalog_item_version = var.catalog_item_version
  # description - (optional) is a type of string
  description = var.description
  # expand_last_request - (optional) is a type of bool
  expand_last_request = var.expand_last_request
  # expand_project - (optional) is a type of bool
  expand_project = var.expand_project
  # expand_resources - (optional) is a type of bool
  expand_resources = var.expand_resources
  # inputs - (optional) is a type of map of string
  inputs = var.inputs
  # lease_expire_at - (optional) is a type of string
  lease_expire_at = var.lease_expire_at
  # name - (required) is a type of string
  name = var.name
  # owner - (optional) is a type of string
  owner = var.owner
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "blueprint_id" {
  description = "returns a string"
  value       = vra_deployment.this.blueprint_id
}

output "blueprint_version" {
  description = "returns a string"
  value       = vra_deployment.this.blueprint_version
}

output "catalog_item_id" {
  description = "returns a string"
  value       = vra_deployment.this.catalog_item_id
}

output "catalog_item_version" {
  description = "returns a string"
  value       = vra_deployment.this.catalog_item_version
}

output "created_at" {
  description = "returns a string"
  value       = vra_deployment.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = vra_deployment.this.created_by
}

output "expense" {
  description = "returns a set of object"
  value       = vra_deployment.this.expense
}

output "id" {
  description = "returns a string"
  value       = vra_deployment.this.id
}

output "inputs_including_defaults" {
  description = "returns a map of string"
  value       = vra_deployment.this.inputs_including_defaults
}

output "last_request" {
  description = "returns a list of object"
  value       = vra_deployment.this.last_request
}

output "last_updated_at" {
  description = "returns a string"
  value       = vra_deployment.this.last_updated_at
}

output "last_updated_by" {
  description = "returns a string"
  value       = vra_deployment.this.last_updated_by
}

output "lease_expire_at" {
  description = "returns a string"
  value       = vra_deployment.this.lease_expire_at
}

output "org_id" {
  description = "returns a string"
  value       = vra_deployment.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_deployment.this.owner
}

output "project" {
  description = "returns a set of object"
  value       = vra_deployment.this.project
}

output "resources" {
  description = "returns a list of object"
  value       = vra_deployment.this.resources
}

output "status" {
  description = "returns a string"
  value       = vra_deployment.this.status
}

output "this" {
  value = vra_deployment.this
}
```

[top](#index)