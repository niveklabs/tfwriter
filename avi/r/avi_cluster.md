# avi_cluster

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/avi/r/avi_cluster"

  # name - (required) is a type of string
  name = null
  # rejoin_nodes_automatically - (optional) is a type of bool
  rejoin_nodes_automatically = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  cluster_state = [{
    progress = null
    state    = null
    up_since = null
  }]

  nodes = [{
    categories = []
    ip = [{
      addr = null
      type = null
    }]
    name     = null
    password = null
    public_ip_or_name = [{
      addr = null
      type = null
    }]
    vm_hostname = null
    vm_mor      = null
    vm_name     = null
    vm_uuid     = null
  }]

  virtual_ip = [{
    addr = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "rejoin_nodes_automatically" {
  description = "(optional)"
  type        = bool
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

variable "nodes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      categories = list(string)
      ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      name     = string
      password = string
      public_ip_or_name = set(object(
        {
          addr = string
          type = string
        }
      ))
      vm_hostname = string
      vm_mor      = string
      vm_name     = string
      vm_uuid     = string
    }
  ))
  default = []
}

variable "virtual_ip" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      addr = string
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_cluster" "this" {
  name                       = var.name
  rejoin_nodes_automatically = var.rejoin_nodes_automatically
  tenant_ref                 = var.tenant_ref
  uuid                       = var.uuid

  dynamic "cluster_state" {
    for_each = var.cluster_state
    content {
      progress = cluster_state.value["progress"]
      state    = cluster_state.value["state"]
      up_since = cluster_state.value["up_since"]
    }
  }

  dynamic "nodes" {
    for_each = var.nodes
    content {
      categories  = nodes.value["categories"]
      name        = nodes.value["name"]
      password    = nodes.value["password"]
      vm_hostname = nodes.value["vm_hostname"]
      vm_mor      = nodes.value["vm_mor"]
      vm_name     = nodes.value["vm_name"]
      vm_uuid     = nodes.value["vm_uuid"]

      dynamic "ip" {
        for_each = nodes.value.ip
        content {
          addr = ip.value["addr"]
          type = ip.value["type"]
        }
      }

      dynamic "public_ip_or_name" {
        for_each = nodes.value.public_ip_or_name
        content {
          addr = public_ip_or_name.value["addr"]
          type = public_ip_or_name.value["type"]
        }
      }

    }
  }

  dynamic "virtual_ip" {
    for_each = var.virtual_ip
    content {
      addr = virtual_ip.value["addr"]
      type = virtual_ip.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_cluster.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_cluster.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_cluster.this.uuid
}

output "this" {
  value = avi_cluster.this
}
```

[top](#index)