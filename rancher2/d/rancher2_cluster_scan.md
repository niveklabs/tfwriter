# rancher2_cluster_scan

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
module "rancher2_cluster_scan" {
  source = "./modules/rancher2/d/rancher2_cluster_scan"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - The cluster ID to scan"
  type        = string
}

variable "name" {
  description = "(optional) - The cluster scan name"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_cluster_scan" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_scan.this.annotations
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cluster_scan.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_scan.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.rancher2_cluster_scan.this.name
}

output "run_type" {
  description = "returns a string"
  value       = data.rancher2_cluster_scan.this.run_type
}

output "scan_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_scan.this.scan_config
}

output "scan_type" {
  description = "returns a string"
  value       = data.rancher2_cluster_scan.this.scan_type
}

output "status" {
  description = "returns a string"
  value       = data.rancher2_cluster_scan.this.status
}

output "this" {
  value = rancher2_cluster_scan.this
}
```

[top](#index)