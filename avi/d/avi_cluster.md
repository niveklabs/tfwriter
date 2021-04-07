# avi_cluster

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_cluster" {
  source = "./modules/avi/d/avi_cluster"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  cluster_state = [{
    progress = null
    state    = null
    up_since = null
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

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_state" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      progress = number
      state    = string
      up_since = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "avi_cluster" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "cluster_state" {
    for_each = var.cluster_state
    content {
      # progress - (optional) is a type of number
      progress = cluster_state.value["progress"]
      # state - (optional) is a type of string
      state = cluster_state.value["state"]
      # up_since - (optional) is a type of string
      up_since = cluster_state.value["up_since"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.avi_cluster.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_cluster.this.name
}

output "nodes" {
  description = "returns a list of object"
  value       = data.avi_cluster.this.nodes
}

output "rejoin_nodes_automatically" {
  description = "returns a bool"
  value       = data.avi_cluster.this.rejoin_nodes_automatically
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_cluster.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_cluster.this.uuid
}

output "virtual_ip" {
  description = "returns a set of object"
  value       = data.avi_cluster.this.virtual_ip
}

output "this" {
  value = avi_cluster.this
}
```

[top](#index)