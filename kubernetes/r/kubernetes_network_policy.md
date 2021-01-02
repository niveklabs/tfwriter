# kubernetes_network_policy

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
module "kubernetes_network_policy" {
  source = "./modules/kubernetes/r/kubernetes_network_policy"


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
    egress = [{
      ports = [{
        port     = null
        protocol = null
      }]
      to = [{
        ip_block = [{
          cidr   = null
          except = []
        }]
        namespace_selector = [{
          match_expressions = [{
            key      = null
            operator = null
            values   = []
          }]
          match_labels = {}
        }]
        pod_selector = [{
          match_expressions = [{
            key      = null
            operator = null
            values   = []
          }]
          match_labels = {}
        }]
      }]
    }]
    ingress = [{
      from = [{
        ip_block = [{
          cidr   = null
          except = []
        }]
        namespace_selector = [{
          match_expressions = [{
            key      = null
            operator = null
            values   = []
          }]
          match_labels = {}
        }]
        pod_selector = [{
          match_expressions = [{
            key      = null
            operator = null
            values   = []
          }]
          match_labels = {}
        }]
      }]
      ports = [{
        port     = null
        protocol = null
      }]
    }]
    pod_selector = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
    }]
    policy_types = []
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
      egress = list(object(
        {
          ports = list(object(
            {
              port     = string
              protocol = string
            }
          ))
          to = list(object(
            {
              ip_block = list(object(
                {
                  cidr   = string
                  except = list(string)
                }
              ))
              namespace_selector = list(object(
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
              pod_selector = list(object(
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
      ))
      ingress = list(object(
        {
          from = list(object(
            {
              ip_block = list(object(
                {
                  cidr   = string
                  except = list(string)
                }
              ))
              namespace_selector = list(object(
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
              pod_selector = list(object(
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
          ports = list(object(
            {
              port     = string
              protocol = string
            }
          ))
        }
      ))
      pod_selector = list(object(
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
      policy_types = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_network_policy" "this" {

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
      policy_types = spec.value["policy_types"]

      dynamic "egress" {
        for_each = spec.value.egress
        content {

          dynamic "ports" {
            for_each = egress.value.ports
            content {
              port     = ports.value["port"]
              protocol = ports.value["protocol"]
            }
          }

          dynamic "to" {
            for_each = egress.value.to
            content {

              dynamic "ip_block" {
                for_each = to.value.ip_block
                content {
                  cidr   = ip_block.value["cidr"]
                  except = ip_block.value["except"]
                }
              }

              dynamic "namespace_selector" {
                for_each = to.value.namespace_selector
                content {
                  match_labels = namespace_selector.value["match_labels"]

                  dynamic "match_expressions" {
                    for_each = namespace_selector.value.match_expressions
                    content {
                      key      = match_expressions.value["key"]
                      operator = match_expressions.value["operator"]
                      values   = match_expressions.value["values"]
                    }
                  }

                }
              }

              dynamic "pod_selector" {
                for_each = to.value.pod_selector
                content {
                  match_labels = pod_selector.value["match_labels"]

                  dynamic "match_expressions" {
                    for_each = pod_selector.value.match_expressions
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
      }

      dynamic "ingress" {
        for_each = spec.value.ingress
        content {

          dynamic "from" {
            for_each = ingress.value.from
            content {

              dynamic "ip_block" {
                for_each = from.value.ip_block
                content {
                  cidr   = ip_block.value["cidr"]
                  except = ip_block.value["except"]
                }
              }

              dynamic "namespace_selector" {
                for_each = from.value.namespace_selector
                content {
                  match_labels = namespace_selector.value["match_labels"]

                  dynamic "match_expressions" {
                    for_each = namespace_selector.value.match_expressions
                    content {
                      key      = match_expressions.value["key"]
                      operator = match_expressions.value["operator"]
                      values   = match_expressions.value["values"]
                    }
                  }

                }
              }

              dynamic "pod_selector" {
                for_each = from.value.pod_selector
                content {
                  match_labels = pod_selector.value["match_labels"]

                  dynamic "match_expressions" {
                    for_each = pod_selector.value.match_expressions
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

          dynamic "ports" {
            for_each = ingress.value.ports
            content {
              port     = ports.value["port"]
              protocol = ports.value["protocol"]
            }
          }

        }
      }

      dynamic "pod_selector" {
        for_each = spec.value.pod_selector
        content {
          match_labels = pod_selector.value["match_labels"]

          dynamic "match_expressions" {
            for_each = pod_selector.value.match_expressions
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
  value       = kubernetes_network_policy.this.id
}

output "this" {
  value = kubernetes_network_policy.this
}
```

[top](#index)