# kubernetes_pod_disruption_budget

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
module "kubernetes_pod_disruption_budget" {
  source = "./modules/kubernetes/r/kubernetes_pod_disruption_budget"


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
    max_unavailable = null
    min_available   = null
    selector = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
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
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      max_unavailable = string
      min_available   = string
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
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_pod_disruption_budget" "this" {

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
      max_unavailable = spec.value["max_unavailable"]
      min_available   = spec.value["min_available"]

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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_pod_disruption_budget.this.id
}

output "this" {
  value = kubernetes_pod_disruption_budget.this
}
```

[top](#index)