# kubernetes_limit_range

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

variable "spec" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
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

```hcl
resource "kubernetes_limit_range" "this" {

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

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "limit" {
        for_each = spec.value.limit
        content {
          default                 = limit.value["default"]
          default_request         = limit.value["default_request"]
          max                     = limit.value["max"]
          max_limit_request_ratio = limit.value["max_limit_request_ratio"]
          min                     = limit.value["min"]
          type                    = limit.value["type"]
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
  value       = kubernetes_limit_range.this.id
}

output "this" {
  value = kubernetes_limit_range.this
}
```

[top](#index)