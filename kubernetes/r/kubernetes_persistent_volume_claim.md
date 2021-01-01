# kubernetes_persistent_volume_claim

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
module "kubernetes_persistent_volume_claim" {
  source = "./modules/kubernetes/r/kubernetes_persistent_volume_claim"

  # wait_until_bound - (optional) is a type of bool
  wait_until_bound = null

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
    access_modes = []
    resources = [{
      limits   = {}
      requests = {}
    }]
    selector = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
    }]
    storage_class_name = null
    volume_name        = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "wait_until_bound" {
  description = "(optional) - Whether to wait for the claim to reach `Bound` state (to find volume in which to claim the space)"
  type        = bool
  default     = null
}

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
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      access_modes = set(string)
      resources = list(object(
        {
          limits   = map(string)
          requests = map(string)
        }
      ))
      selector = list(object(
        {
          match_expressions = list(object(
            {
              key      = string
              operator = string
              values   = set(string)
            }
          ))
          match_labels = map(string)
        }
      ))
      storage_class_name = string
      volume_name        = string
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "kubernetes_persistent_volume_claim" "this" {
  wait_until_bound = var.wait_until_bound

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
      access_modes       = spec.value["access_modes"]
      storage_class_name = spec.value["storage_class_name"]
      volume_name        = spec.value["volume_name"]

      dynamic "resources" {
        for_each = spec.value.resources
        content {
          limits   = resources.value["limits"]
          requests = resources.value["requests"]
        }
      }

      dynamic "selector" {
        for_each = spec.value.selector
        content {
          match_labels = selector.value["match_labels"]

          dynamic "match_expressions" {
            for_each = selector.value.match_expressions
            content {
              key      = match_expressions.value["key"]
              operator = match_expressions.value["operator"]
              values   = match_expressions.value["values"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = kubernetes_persistent_volume_claim.this.id
}

output "this" {
  value = kubernetes_persistent_volume_claim.this
}
```

[top](#index)