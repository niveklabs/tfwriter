# alicloud_edas_cluster

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_edas_cluster" {
  source = "./modules/alicloud/r/alicloud_edas_cluster"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # cluster_type - (required) is a type of number
  cluster_type = null
  # logical_region_id - (optional) is a type of string
  logical_region_id = null
  # network_mode - (required) is a type of number
  network_mode = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "cluster_type" {
  description = "(required)"
  type        = number
}

variable "logical_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_mode" {
  description = "(required)"
  type        = number
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_cluster" "this" {
  cluster_name      = var.cluster_name
  cluster_type      = var.cluster_type
  logical_region_id = var.logical_region_id
  network_mode      = var.network_mode
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_edas_cluster.this.id
}

output "this" {
  value = alicloud_edas_cluster.this
}
```

[top](#index)