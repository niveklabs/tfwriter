# kubernetes_endpoints

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
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

```terraform
variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
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
  description = "nested block: NestingSet, min items: 0, max items: 0"
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

```terraform
resource "kubernetes_endpoints" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # annotations - (optional) is a type of map of string
      annotations = metadata.value["annotations"]
      # generate_name - (optional) is a type of string
      generate_name = metadata.value["generate_name"]
      # labels - (optional) is a type of map of string
      labels = metadata.value["labels"]
      # name - (optional) is a type of string
      name = metadata.value["name"]
      # namespace - (optional) is a type of string
      namespace = metadata.value["namespace"]
    }
  }

  dynamic "subset" {
    for_each = var.subset
    content {

      dynamic "address" {
        for_each = subset.value.address
        content {
          # hostname - (optional) is a type of string
          hostname = address.value["hostname"]
          # ip - (required) is a type of string
          ip = address.value["ip"]
          # node_name - (optional) is a type of string
          node_name = address.value["node_name"]
        }
      }

      dynamic "not_ready_address" {
        for_each = subset.value.not_ready_address
        content {
          # hostname - (optional) is a type of string
          hostname = not_ready_address.value["hostname"]
          # ip - (required) is a type of string
          ip = not_ready_address.value["ip"]
          # node_name - (optional) is a type of string
          node_name = not_ready_address.value["node_name"]
        }
      }

      dynamic "port" {
        for_each = subset.value.port
        content {
          # name - (optional) is a type of string
          name = port.value["name"]
          # port - (required) is a type of number
          port = port.value["port"]
          # protocol - (optional) is a type of string
          protocol = port.value["protocol"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_endpoints.this.id
}

output "this" {
  value = kubernetes_endpoints.this
}
```

[top](#index)