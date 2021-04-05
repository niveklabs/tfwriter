# profitbricks_k8s_cluster

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_k8s_cluster" {
  source = "./modules/profitbricks/d/profitbricks_k8s_cluster"

  # name - (optional) is a type of string
  name = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "profitbricks_k8s_cluster" "this" {
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.profitbricks_k8s_cluster.this.id
}

output "k8s_version" {
  description = "returns a string"
  value       = data.profitbricks_k8s_cluster.this.k8s_version
}

output "kube_config" {
  description = "returns a string"
  value       = data.profitbricks_k8s_cluster.this.kube_config
}

output "node_pools" {
  description = "returns a list of string"
  value       = data.profitbricks_k8s_cluster.this.node_pools
}

output "state" {
  description = "returns a string"
  value       = data.profitbricks_k8s_cluster.this.state
}

output "this" {
  value = profitbricks_k8s_cluster.this
}
```

[top](#index)