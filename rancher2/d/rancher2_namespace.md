# rancher2_namespace

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
module "rancher2_namespace" {
  source = "./modules/rancher2/d/rancher2_namespace"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the k8s namespace managed by rancher v2"
  type        = string
}

variable "project_id" {
  description = "(required) - Project ID where k8s namespace belongs"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_namespace" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_namespace.this.annotations
}

output "container_resource_limit" {
  description = "returns a list of object"
  value       = data.rancher2_namespace.this.container_resource_limit
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_namespace.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_namespace.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_namespace.this.labels
}

output "resource_quota" {
  description = "returns a list of object"
  value       = data.rancher2_namespace.this.resource_quota
}

output "this" {
  value = rancher2_namespace.this
}
```

[top](#index)