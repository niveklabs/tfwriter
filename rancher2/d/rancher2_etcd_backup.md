# rancher2_etcd_backup

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
module "rancher2_etcd_backup" {
  source = "./modules/rancher2/d/rancher2_etcd_backup"

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
data "rancher2_etcd_backup" "this" {
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
  value       = data.rancher2_etcd_backup.this.annotations
}

output "backup_config" {
  description = "returns a list of object"
  value       = data.rancher2_etcd_backup.this.backup_config
}

output "filename" {
  description = "returns a string"
  value       = data.rancher2_etcd_backup.this.filename
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_etcd_backup.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_etcd_backup.this.labels
}

output "manual" {
  description = "returns a bool"
  value       = data.rancher2_etcd_backup.this.manual
}

output "namespace_id" {
  description = "returns a string"
  value       = data.rancher2_etcd_backup.this.namespace_id
}

output "this" {
  value = rancher2_etcd_backup.this
}
```

[top](#index)