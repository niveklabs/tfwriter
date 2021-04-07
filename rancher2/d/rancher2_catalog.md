# rancher2_catalog

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
module "rancher2_catalog" {
  source = "./modules/rancher2/d/rancher2_catalog"

  # name - (required) is a type of string
  name = null
  # scope - (optional) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_catalog" "this" {
  # name - (required) is a type of string
  name = var.name
  # scope - (optional) is a type of string
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_catalog.this.annotations
}

output "branch" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.branch
}

output "cluster_id" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.cluster_id
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.id
}

output "kind" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.kind
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_catalog.this.labels
}

output "password" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.password
  sensitive   = true
}

output "project_id" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.project_id
}

output "url" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.url
}

output "username" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.username
  sensitive   = true
}

output "version" {
  description = "returns a string"
  value       = data.rancher2_catalog.this.version
}

output "this" {
  value = rancher2_catalog.this
}
```

[top](#index)