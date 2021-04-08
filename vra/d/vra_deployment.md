# vra_deployment

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
module "vra_deployment" {
  source = "./modules/vra/d/vra_deployment"

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
  # created_at - (optional) is a type of string
  created_at = null
  # created_by - (optional) is a type of string
  created_by = null
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
  # last_updated_at - (optional) is a type of string
  last_updated_at = null
  # last_updated_by - (optional) is a type of string
  last_updated_by = null
  # lease_expire_at - (optional) is a type of string
  lease_expire_at = null
  # name - (optional) is a type of string
  name = null
  # owner - (optional) is a type of string
  owner = null
  # project_id - (optional) is a type of string
  project_id = null
  # status - (optional) is a type of string
  status = null
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

variable "created_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
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
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "last_updated_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_updated_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lease_expire_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vra_deployment" "this" {
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
  # created_at - (optional) is a type of string
  created_at = var.created_at
  # created_by - (optional) is a type of string
  created_by = var.created_by
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
  # last_updated_at - (optional) is a type of string
  last_updated_at = var.last_updated_at
  # last_updated_by - (optional) is a type of string
  last_updated_by = var.last_updated_by
  # lease_expire_at - (optional) is a type of string
  lease_expire_at = var.lease_expire_at
  # name - (optional) is a type of string
  name = var.name
  # owner - (optional) is a type of string
  owner = var.owner
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "blueprint_content" {
  description = "returns a string"
  value       = data.vra_deployment.this.blueprint_content
}

output "blueprint_id" {
  description = "returns a string"
  value       = data.vra_deployment.this.blueprint_id
}

output "blueprint_version" {
  description = "returns a string"
  value       = data.vra_deployment.this.blueprint_version
}

output "catalog_item_id" {
  description = "returns a string"
  value       = data.vra_deployment.this.catalog_item_id
}

output "catalog_item_version" {
  description = "returns a string"
  value       = data.vra_deployment.this.catalog_item_version
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_deployment.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = data.vra_deployment.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.vra_deployment.this.description
}

output "expense" {
  description = "returns a set of object"
  value       = data.vra_deployment.this.expense
}

output "id" {
  description = "returns a string"
  value       = data.vra_deployment.this.id
}

output "inputs" {
  description = "returns a map of string"
  value       = data.vra_deployment.this.inputs
}

output "last_request" {
  description = "returns a list of object"
  value       = data.vra_deployment.this.last_request
}

output "last_updated_at" {
  description = "returns a string"
  value       = data.vra_deployment.this.last_updated_at
}

output "last_updated_by" {
  description = "returns a string"
  value       = data.vra_deployment.this.last_updated_by
}

output "lease_expire_at" {
  description = "returns a string"
  value       = data.vra_deployment.this.lease_expire_at
}

output "name" {
  description = "returns a string"
  value       = data.vra_deployment.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_deployment.this.org_id
}

output "project" {
  description = "returns a set of object"
  value       = data.vra_deployment.this.project
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_deployment.this.project_id
}

output "resources" {
  description = "returns a list of object"
  value       = data.vra_deployment.this.resources
}

output "status" {
  description = "returns a string"
  value       = data.vra_deployment.this.status
}

output "this" {
  value = vra_deployment.this
}
```

[top](#index)