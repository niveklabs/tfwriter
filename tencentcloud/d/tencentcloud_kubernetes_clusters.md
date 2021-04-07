# tencentcloud_kubernetes_clusters

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
module "tencentcloud_kubernetes_clusters" {
  source = "./modules/tencentcloud/d/tencentcloud_kubernetes_clusters"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional) - ID of the cluster. Conflict with cluster_name, can not be set at the same time."
  type        = string
  default     = null
}

variable "cluster_name" {
  description = "(optional) - Name of the cluster. Conflict with cluster_id, can not be set at the same time."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the cluster."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_kubernetes_clusters" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # cluster_name - (optional) is a type of string
  cluster_name = var.cluster_name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_kubernetes_clusters.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_kubernetes_clusters.this.list
}

output "this" {
  value = tencentcloud_kubernetes_clusters.this
}
```

[top](#index)