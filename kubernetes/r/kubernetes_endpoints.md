# kubernetes_endpoints

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "kubernetes_endpoints" {
  source = "./modules/kubernetes/r/kubernetes_endpoints"


  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    namespace        = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  subset = [{
    address = [{
      hostname  = null
      ip        = null
      node_name = null
    }]
    not_ready_address = [{
      hostname  = null
      ip        = null
      node_name = null
    }]
    port = [{
      name     = null
      port     = null
      protocol = null
    }]
  }]
}
```

[top](#index)

### Variables

```hcl
variable "metadata" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generate_name    = string
      generation       = number
      labels           = map(string)
      name             = string
      namespace        = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "subset" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address = set(object(
        {
          hostname  = string
          ip        = string
          node_name = string
        }
      ))
      not_ready_address = set(object(
        {
          hostname  = string
          ip        = string
          node_name = string
        }
      ))
      port = set(object(
        {
          name     = string
          port     = number
          protocol = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "kubernetes_endpoints" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
      namespace     = metadata.value["namespace"]
    }
  }

  dynamic "subset" {
    for_each = var.subset
    content {

      dynamic "address" {
        for_each = subset.value.address
        content {
          hostname  = address.value["hostname"]
          ip        = address.value["ip"]
          node_name = address.value["node_name"]
        }
      }

      dynamic "not_ready_address" {
        for_each = subset.value.not_ready_address
        content {
          hostname  = not_ready_address.value["hostname"]
          ip        = not_ready_address.value["ip"]
          node_name = not_ready_address.value["node_name"]
        }
      }

      dynamic "port" {
        for_each = subset.value.port
        content {
          name     = port.value["name"]
          port     = port.value["port"]
          protocol = port.value["protocol"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = kubernetes_endpoints.this.id
}

output "this" {
  value = kubernetes_endpoints.this
}
```

[top](#index)