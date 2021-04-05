# rancher2_registry

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
module "rancher2_registry" {
  source = "./modules/rancher2/d/rancher2_registry"

  # name - (required) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the docker registry"
  type        = string
}

variable "namespace_id" {
  description = "(optional) - Namespace ID to add docker registry"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - Project ID to add docker registry"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_registry" "this" {
  name         = var.name
  namespace_id = var.namespace_id
  project_id   = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_registry.this.annotations
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_registry.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_registry.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_registry.this.labels
}

output "registries" {
  description = "returns a list of object"
  value       = data.rancher2_registry.this.registries
}

output "this" {
  value = rancher2_registry.this
}
```

[top](#index)