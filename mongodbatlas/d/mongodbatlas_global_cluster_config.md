# mongodbatlas_global_cluster_config

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_global_cluster_config" {
  source = "./modules/mongodbatlas/d/mongodbatlas_global_cluster_config"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # project_id - (required) is a type of string
  project_id = null

  managed_namespaces = [{
    collection       = null
    custom_shard_key = null
    db               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "managed_namespaces" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      collection       = string
      custom_shard_key = string
      db               = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_global_cluster_config" "this" {
  cluster_name = var.cluster_name
  project_id   = var.project_id

  dynamic "managed_namespaces" {
    for_each = var.managed_namespaces
    content {
      collection       = managed_namespaces.value["collection"]
      custom_shard_key = managed_namespaces.value["custom_shard_key"]
      db               = managed_namespaces.value["db"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "custom_zone_mapping" {
  description = "returns a map of string"
  value       = data.mongodbatlas_global_cluster_config.this.custom_zone_mapping
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_global_cluster_config.this.id
}

output "this" {
  value = mongodbatlas_global_cluster_config.this
}
```

[top](#index)