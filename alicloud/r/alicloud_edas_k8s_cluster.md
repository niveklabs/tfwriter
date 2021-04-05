# alicloud_edas_k8s_cluster

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_edas_k8s_cluster" {
  source = "./modules/alicloud/r/alicloud_edas_k8s_cluster"

  # cs_cluster_id - (required) is a type of string
  cs_cluster_id = null
  # namespace_id - (optional) is a type of string
  namespace_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cs_cluster_id" {
  description = "(required)"
  type        = string
}

variable "namespace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_k8s_cluster" "this" {
  cs_cluster_id = var.cs_cluster_id
  namespace_id  = var.namespace_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_import_status" {
  description = "returns a number"
  value       = alicloud_edas_k8s_cluster.this.cluster_import_status
}

output "cluster_name" {
  description = "returns a string"
  value       = alicloud_edas_k8s_cluster.this.cluster_name
}

output "cluster_type" {
  description = "returns a number"
  value       = alicloud_edas_k8s_cluster.this.cluster_type
}

output "id" {
  description = "returns a string"
  value       = alicloud_edas_k8s_cluster.this.id
}

output "network_mode" {
  description = "returns a number"
  value       = alicloud_edas_k8s_cluster.this.network_mode
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_edas_k8s_cluster.this.vpc_id
}

output "this" {
  value = alicloud_edas_k8s_cluster.this
}
```

[top](#index)