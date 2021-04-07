# rancher2_catalog_v2

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
module "rancher2_catalog_v2" {
  source = "./modules/rancher2/d/rancher2_catalog_v2"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null
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
```

[top](#index)

### Datasource

```terraform
data "rancher2_catalog_v2" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_catalog_v2.this.annotations
}

output "ca_bundle" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.ca_bundle
}

output "enabled" {
  description = "returns a bool"
  value       = data.rancher2_catalog_v2.this.enabled
}

output "git_branch" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.git_branch
}

output "git_repo" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.git_repo
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.id
}

output "insecure" {
  description = "returns a bool"
  value       = data.rancher2_catalog_v2.this.insecure
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_catalog_v2.this.labels
}

output "resource_version" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.resource_version
}

output "secret_name" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.secret_name
}

output "secret_namespace" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.secret_namespace
}

output "service_account" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.service_account
}

output "service_account_namespace" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.service_account_namespace
}

output "url" {
  description = "returns a string"
  value       = data.rancher2_catalog_v2.this.url
}

output "this" {
  value = rancher2_catalog_v2.this
}
```

[top](#index)