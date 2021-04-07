# tencentcloud_container_cluster_instances

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
module "tencentcloud_container_cluster_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_container_cluster_instances"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # limit - (optional) is a type of number
  limit = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - An ID identify the cluster, like cls-xxxxxx."
  type        = string
}

variable "limit" {
  description = "(optional) - An int variable describe how many instances in return at most."
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_container_cluster_instances" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # limit - (optional) is a type of number
  limit = var.limit
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_container_cluster_instances.this.id
}

output "nodes" {
  description = "returns a list of object"
  value       = data.tencentcloud_container_cluster_instances.this.nodes
}

output "total_count" {
  description = "returns a number"
  value       = data.tencentcloud_container_cluster_instances.this.total_count
}

output "this" {
  value = tencentcloud_container_cluster_instances.this
}
```

[top](#index)