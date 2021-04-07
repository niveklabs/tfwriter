# tencentcloud_container_clusters

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_container_clusters" {
  source = "./modules/tencentcloud/d/tencentcloud_container_clusters"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # limit - (optional) is a type of number
  limit = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional) - An id identify the cluster, like `cls-xxxxxx`."
  type        = string
  default     = null
}

variable "limit" {
  description = "(optional) - An int variable describe how many cluster in return at most."
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_container_clusters" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # limit - (optional) is a type of number
  limit = var.limit
}
```

[top](#index)

### Outputs

```terraform
output "clusters" {
  description = "returns a list of object"
  value       = data.tencentcloud_container_clusters.this.clusters
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_container_clusters.this.id
}

output "total_count" {
  description = "returns a number"
  value       = data.tencentcloud_container_clusters.this.total_count
}

output "this" {
  value = tencentcloud_container_clusters.this
}
```

[top](#index)