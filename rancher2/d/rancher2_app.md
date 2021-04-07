# rancher2_app

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_app" {
  source = "./modules/rancher2/d/rancher2_app"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # target_namespace - (optional) is a type of string
  target_namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the app"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the app"
  type        = string
}

variable "project_id" {
  description = "(required) - Project ID to add app"
  type        = string
}

variable "target_namespace" {
  description = "(optional) - Namespace name to add app"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_app" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # target_namespace - (optional) is a type of string
  target_namespace = var.target_namespace
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_app.this.annotations
}

output "answers" {
  description = "returns a map of string"
  value       = data.rancher2_app.this.answers
}

output "catalog_name" {
  description = "returns a string"
  value       = data.rancher2_app.this.catalog_name
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_app.this.description
}

output "external_id" {
  description = "returns a string"
  value       = data.rancher2_app.this.external_id
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_app.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_app.this.labels
}

output "revision_id" {
  description = "returns a string"
  value       = data.rancher2_app.this.revision_id
}

output "target_namespace" {
  description = "returns a string"
  value       = data.rancher2_app.this.target_namespace
}

output "template_name" {
  description = "returns a string"
  value       = data.rancher2_app.this.template_name
}

output "template_version" {
  description = "returns a string"
  value       = data.rancher2_app.this.template_version
}

output "values_yaml" {
  description = "returns a string"
  value       = data.rancher2_app.this.values_yaml
}

output "this" {
  value = rancher2_app.this
}
```

[top](#index)