# linode_lke_cluster

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_lke_cluster" {
  source = "./modules/linode/r/linode_lke_cluster"

  # k8s_version - (required) is a type of string
  k8s_version = null
  # label - (required) is a type of string
  label = null
  # region - (required) is a type of string
  region = null
  # tags - (optional) is a type of set of string
  tags = []

  pool = [{
    count = null
    id    = null
    nodes = [{
      id          = null
      instance_id = null
      status      = null
    }]
    type = null
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
variable "k8s_version" {
  description = "(required) - The desired Kubernetes version for this Kubernetes cluster in the format of <major>.<minor>. The latest supported patch version will be deployed."
  type        = string
}

variable "label" {
  description = "(required) - The unique label for the cluster."
  type        = string
}

variable "region" {
  description = "(required) - This cluster's location."
  type        = string
}

variable "tags" {
  description = "(optional) - An array of tags applied to this object. Tags are for organizational purposes only."
  type        = set(string)
  default     = null
}

variable "pool" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      count = number
      id    = number
      nodes = list(object(
        {
          id          = string
          instance_id = number
          status      = string
        }
      ))
      type = string
    }
  ))
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
resource "linode_lke_cluster" "this" {
  k8s_version = var.k8s_version
  label       = var.label
  region      = var.region
  tags        = var.tags

  dynamic "pool" {
    for_each = var.pool
    content {
      count = pool.value["count"]
      type  = pool.value["type"]
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
output "api_endpoints" {
  description = "returns a list of string"
  value       = linode_lke_cluster.this.api_endpoints
}

output "id" {
  description = "returns a string"
  value       = linode_lke_cluster.this.id
}

output "kubeconfig" {
  description = "returns a string"
  value       = linode_lke_cluster.this.kubeconfig
  sensitive   = true
}

output "status" {
  description = "returns a string"
  value       = linode_lke_cluster.this.status
}

output "this" {
  value = linode_lke_cluster.this
}
```

[top](#index)