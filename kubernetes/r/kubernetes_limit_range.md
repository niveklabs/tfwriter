# kubernetes_limit_range

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
module "kubernetes_limit_range" {
  source = "./modules/kubernetes/r/kubernetes_limit_range"


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

  spec = [{
    limit = [{
      default                 = {}
      default_request         = {}
      max                     = {}
      max_limit_request_ratio = {}
      min                     = {}
      type                    = null
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

variable "spec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      limit = list(object(
        {
          default                 = map(string)
          default_request         = map(string)
          max                     = map(string)
          max_limit_request_ratio = map(string)
          min                     = map(string)
          type                    = string
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
resource "kubernetes_limit_range" "this" {

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

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "limit" {
        for_each = spec.value.limit
        content {
          # default - (optional) is a type of map of string
          default = limit.value["default"]
          # default_request - (optional) is a type of map of string
          default_request = limit.value["default_request"]
          # max - (optional) is a type of map of string
          max = limit.value["max"]
          # max_limit_request_ratio - (optional) is a type of map of string
          max_limit_request_ratio = limit.value["max_limit_request_ratio"]
          # min - (optional) is a type of map of string
          min = limit.value["min"]
          # type - (optional) is a type of string
          type = limit.value["type"]
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
  value       = kubernetes_limit_range.this.id
}

output "this" {
  value = kubernetes_limit_range.this
}
```

[top](#index)