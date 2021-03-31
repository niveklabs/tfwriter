# alicloud_cs_kubernetes_autoscaler

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_kubernetes_autoscaler" {
  source = "./modules/alicloud/r/alicloud_cs_kubernetes_autoscaler"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # cool_down_duration - (required) is a type of string
  cool_down_duration = null
  # defer_scale_in_duration - (required) is a type of string
  defer_scale_in_duration = null
  # use_ecs_ram_role_token - (optional) is a type of bool
  use_ecs_ram_role_token = null
  # utilization - (required) is a type of string
  utilization = null

  nodepools = [{
    id     = null
    labels = null
    taints = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "cool_down_duration" {
  description = "(required)"
  type        = string
}

variable "defer_scale_in_duration" {
  description = "(required)"
  type        = string
}

variable "use_ecs_ram_role_token" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "utilization" {
  description = "(required)"
  type        = string
}

variable "nodepools" {
  description = "nested block: NestingSet, min items: 0, max items: 30"
  type = set(object(
    {
      id     = string
      labels = string
      taints = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cs_kubernetes_autoscaler" "this" {
  cluster_id              = var.cluster_id
  cool_down_duration      = var.cool_down_duration
  defer_scale_in_duration = var.defer_scale_in_duration
  use_ecs_ram_role_token  = var.use_ecs_ram_role_token
  utilization             = var.utilization

  dynamic "nodepools" {
    for_each = var.nodepools
    content {
      id     = nodepools.value["id"]
      labels = nodepools.value["labels"]
      taints = nodepools.value["taints"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes_autoscaler.this.id
}

output "this" {
  value = alicloud_cs_kubernetes_autoscaler.this
}
```

[top](#index)