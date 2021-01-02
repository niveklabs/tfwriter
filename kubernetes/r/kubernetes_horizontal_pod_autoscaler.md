# kubernetes_horizontal_pod_autoscaler

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
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_horizontal_pod_autoscaler" {
  source = "./modules/kubernetes/r/kubernetes_horizontal_pod_autoscaler"


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
    max_replicas = null
    metric = [{
      external = [{
        metric = [{
          name = null
          selector = [{
            match_expressions = [{
              key      = null
              operator = null
              values   = []
            }]
            match_labels = {}
          }]
        }]
        target = [{
          average_utilization = null
          average_value       = null
          type                = null
          value               = null
        }]
      }]
      object = [{
        described_object = [{
          api_version = null
          kind        = null
          name        = null
        }]
        metric = [{
          name = null
          selector = [{
            match_expressions = [{
              key      = null
              operator = null
              values   = []
            }]
            match_labels = {}
          }]
        }]
        target = [{
          average_utilization = null
          average_value       = null
          type                = null
          value               = null
        }]
      }]
      pods = [{
        metric = [{
          name = null
          selector = [{
            match_expressions = [{
              key      = null
              operator = null
              values   = []
            }]
            match_labels = {}
          }]
        }]
        target = [{
          average_utilization = null
          average_value       = null
          type                = null
          value               = null
        }]
      }]
      resource = [{
        name = null
        target = [{
          average_utilization = null
          average_value       = null
          type                = null
          value               = null
        }]
      }]
      type = null
    }]
    min_replicas = null
    scale_target_ref = [{
      api_version = null
      kind        = null
      name        = null
    }]
    target_cpu_utilization_percentage = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
      max_replicas = number
      metric = list(object(
        {
          external = list(object(
            {
              metric = list(object(
                {
                  name = string
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
              target = list(object(
                {
                  average_utilization = number
                  average_value       = string
                  type                = string
                  value               = string
                }
              ))
            }
          ))
          object = list(object(
            {
              described_object = list(object(
                {
                  api_version = string
                  kind        = string
                  name        = string
                }
              ))
              metric = list(object(
                {
                  name = string
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
              target = list(object(
                {
                  average_utilization = number
                  average_value       = string
                  type                = string
                  value               = string
                }
              ))
            }
          ))
          pods = list(object(
            {
              metric = list(object(
                {
                  name = string
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
              target = list(object(
                {
                  average_utilization = number
                  average_value       = string
                  type                = string
                  value               = string
                }
              ))
            }
          ))
          resource = list(object(
            {
              name = string
              target = list(object(
                {
                  average_utilization = number
                  average_value       = string
                  type                = string
                  value               = string
                }
              ))
            }
          ))
          type = string
        }
      ))
      min_replicas = number
      scale_target_ref = list(object(
        {
          api_version = string
          kind        = string
          name        = string
        }
      ))
      target_cpu_utilization_percentage = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_horizontal_pod_autoscaler" "this" {

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
      max_replicas                      = spec.value["max_replicas"]
      min_replicas                      = spec.value["min_replicas"]
      target_cpu_utilization_percentage = spec.value["target_cpu_utilization_percentage"]

      dynamic "metric" {
        for_each = spec.value.metric
        content {
          type = metric.value["type"]

          dynamic "external" {
            for_each = metric.value.external
            content {

              dynamic "metric" {
                for_each = external.value.metric
                content {
                  name = metric.value["name"]

                  dynamic "selector" {
                    for_each = metric.value.selector
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

              dynamic "target" {
                for_each = external.value.target
                content {
                  average_utilization = target.value["average_utilization"]
                  average_value       = target.value["average_value"]
                  type                = target.value["type"]
                  value               = target.value["value"]
                }
              }

            }
          }

          dynamic "object" {
            for_each = metric.value.object
            content {

              dynamic "described_object" {
                for_each = object.value.described_object
                content {
                  api_version = described_object.value["api_version"]
                  kind        = described_object.value["kind"]
                  name        = described_object.value["name"]
                }
              }

              dynamic "metric" {
                for_each = object.value.metric
                content {
                  name = metric.value["name"]

                  dynamic "selector" {
                    for_each = metric.value.selector
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

              dynamic "target" {
                for_each = object.value.target
                content {
                  average_utilization = target.value["average_utilization"]
                  average_value       = target.value["average_value"]
                  type                = target.value["type"]
                  value               = target.value["value"]
                }
              }

            }
          }

          dynamic "pods" {
            for_each = metric.value.pods
            content {

              dynamic "metric" {
                for_each = pods.value.metric
                content {
                  name = metric.value["name"]

                  dynamic "selector" {
                    for_each = metric.value.selector
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

              dynamic "target" {
                for_each = pods.value.target
                content {
                  average_utilization = target.value["average_utilization"]
                  average_value       = target.value["average_value"]
                  type                = target.value["type"]
                  value               = target.value["value"]
                }
              }

            }
          }

          dynamic "resource" {
            for_each = metric.value.resource
            content {
              name = resource.value["name"]

              dynamic "target" {
                for_each = resource.value.target
                content {
                  average_utilization = target.value["average_utilization"]
                  average_value       = target.value["average_value"]
                  type                = target.value["type"]
                  value               = target.value["value"]
                }
              }

            }
          }

        }
      }

      dynamic "scale_target_ref" {
        for_each = spec.value.scale_target_ref
        content {
          api_version = scale_target_ref.value["api_version"]
          kind        = scale_target_ref.value["kind"]
          name        = scale_target_ref.value["name"]
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
  value       = kubernetes_horizontal_pod_autoscaler.this.id
}

output "this" {
  value = kubernetes_horizontal_pod_autoscaler.this
}
```

[top](#index)