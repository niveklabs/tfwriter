# rancher2_secret_v2

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
module "rancher2_secret_v2" {
  source = "./modules/rancher2/d/rancher2_secret_v2"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_secret_v2" "this" {
  cluster_id = var.cluster_id
  name       = var.name
  namespace  = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_secret_v2.this.annotations
}

output "data" {
  description = "returns a map of string"
  value       = data.rancher2_secret_v2.this.data
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_secret_v2.this.id
}

output "immutable" {
  description = "returns a bool"
  value       = data.rancher2_secret_v2.this.immutable
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_secret_v2.this.labels
}

output "resource_version" {
  description = "returns a string"
  value       = data.rancher2_secret_v2.this.resource_version
}

output "type" {
  description = "returns a string"
  value       = data.rancher2_secret_v2.this.type
}

output "this" {
  value = rancher2_secret_v2.this
}
```

[top](#index)