# rancher2_cluster_driver

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
module "rancher2_cluster_driver" {
  source = "./modules/rancher2/d/rancher2_cluster_driver"

  # name - (required) is a type of string
  name = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_cluster_driver" "this" {
  name = var.name
  url  = var.url
}
```

[top](#index)

### Outputs

```terraform
output "active" {
  description = "returns a bool"
  value       = data.rancher2_cluster_driver.this.active
}

output "actual_url" {
  description = "returns a string"
  value       = data.rancher2_cluster_driver.this.actual_url
}

output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_driver.this.annotations
}

output "builtin" {
  description = "returns a bool"
  value       = data.rancher2_cluster_driver.this.builtin
}

output "checksum" {
  description = "returns a string"
  value       = data.rancher2_cluster_driver.this.checksum
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cluster_driver.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_driver.this.labels
}

output "ui_url" {
  description = "returns a string"
  value       = data.rancher2_cluster_driver.this.ui_url
}

output "url" {
  description = "returns a string"
  value       = data.rancher2_cluster_driver.this.url
}

output "whitelist_domains" {
  description = "returns a list of string"
  value       = data.rancher2_cluster_driver.this.whitelist_domains
}

output "this" {
  value = rancher2_cluster_driver.this
}
```

[top](#index)