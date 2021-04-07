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
    kubernetes = ">= 2.0.3"
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
      # max_replicas - (required) is a type of number
      max_replicas = spec.value["max_replicas"]
      # min_replicas - (optional) is a type of number
      min_replicas = spec.value["min_replicas"]
      # target_cpu_utilization_percentage - (optional) is a type of number
      target_cpu_utilization_percentage = spec.value["target_cpu_utilization_percentage"]

      dynamic "metric" {
        for_each = spec.value.metric
        content {
          # type - (required) is a type of string
          type = metric.value["type"]

          dynamic "external" {
            for_each = metric.value.external
            content {

              dynamic "metric" {
                for_each = external.value.metric
                content {
                  # name - (required) is a type of string
                  name = metric.value["name"]

                  dynamic "selector" {
                    for_each = metric.value.selector
                    content {
                      # match_labels - (optional) is a type of map of string
                      match_labels = selector.value["match_labels"]

                      dynamic "match_expressions" {
                        for_each = selector.value.match_expressions
                        content {
                          # key - (optional) is a type of string
                          key = match_expressions.value["key"]
                          # operator - (optional) is a type of string
                          operator = match_expressions.value["operator"]
                          # values - (optional) is a type of set of string
                          values = match_expressions.value["values"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "target" {
                for_each = external.value.target
                content {
                  # average_utilization - (optional) is a type of number
                  average_utilization = target.value["average_utilization"]
                  # average_value - (optional) is a type of string
                  average_value = target.value["average_value"]
                  # type - (required) is a type of string
                  type = target.value["type"]
                  # value - (optional) is a type of string
                  value = target.value["value"]
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
                  # api_version - (required) is a type of string
                  api_version = described_object.value["api_version"]
                  # kind - (required) is a type of string
                  kind = described_object.value["kind"]
                  # name - (required) is a type of string
                  name = described_object.value["name"]
                }
              }

              dynamic "metric" {
                for_each = object.value.metric
                content {
                  # name - (required) is a type of string
                  name = metric.value["name"]

                  dynamic "selector" {
                    for_each = metric.value.selector
                    content {
                      # match_labels - (optional) is a type of map of string
                      match_labels = selector.value["match_labels"]

                      dynamic "match_expressions" {
                        for_each = selector.value.match_expressions
                        content {
                          # key - (optional) is a type of string
                          key = match_expressions.value["key"]
                          # operator - (optional) is a type of string
                          operator = match_expressions.value["operator"]
                          # values - (optional) is a type of set of string
                          values = match_expressions.value["values"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "target" {
                for_each = object.value.target
                content {
                  # average_utilization - (optional) is a type of number
                  average_utilization = target.value["average_utilization"]
                  # average_value - (optional) is a type of string
                  average_value = target.value["average_value"]
                  # type - (required) is a type of string
                  type = target.value["type"]
                  # value - (optional) is a type of string
                  value = target.value["value"]
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
                  # name - (required) is a type of string
                  name = metric.value["name"]

                  dynamic "selector" {
                    for_each = metric.value.selector
                    content {
                      # match_labels - (optional) is a type of map of string
                      match_labels = selector.value["match_labels"]

                      dynamic "match_expressions" {
                        for_each = selector.value.match_expressions
                        content {
                          # key - (optional) is a type of string
                          key = match_expressions.value["key"]
                          # operator - (optional) is a type of string
                          operator = match_expressions.value["operator"]
                          # values - (optional) is a type of set of string
                          values = match_expressions.value["values"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "target" {
                for_each = pods.value.target
                content {
                  # average_utilization - (optional) is a type of number
                  average_utilization = target.value["average_utilization"]
                  # average_value - (optional) is a type of string
                  average_value = target.value["average_value"]
                  # type - (required) is a type of string
                  type = target.value["type"]
                  # value - (optional) is a type of string
                  value = target.value["value"]
                }
              }

            }
          }

          dynamic "resource" {
            for_each = metric.value.resource
            content {
              # name - (required) is a type of string
              name = resource.value["name"]

              dynamic "target" {
                for_each = resource.value.target
                content {
                  # average_utilization - (optional) is a type of number
                  average_utilization = target.value["average_utilization"]
                  # average_value - (optional) is a type of string
                  average_value = target.value["average_value"]
                  # type - (required) is a type of string
                  type = target.value["type"]
                  # value - (optional) is a type of string
                  value = target.value["value"]
                }
              }

            }
          }

        }
      }

      dynamic "scale_target_ref" {
        for_each = spec.value.scale_target_ref
        content {
          # api_version - (optional) is a type of string
          api_version = scale_target_ref.value["api_version"]
          # kind - (required) is a type of string
          kind = scale_target_ref.value["kind"]
          # name - (required) is a type of string
          name = scale_target_ref.value["name"]
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