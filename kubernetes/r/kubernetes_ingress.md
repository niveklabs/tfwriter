# kubernetes_ingress

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
module "kubernetes_ingress" {
  source = "./modules/kubernetes/r/kubernetes_ingress"

  # wait_for_load_balancer - (optional) is a type of bool
  wait_for_load_balancer = null

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
    backend = [{
      service_name = null
      service_port = null
    }]
    ingress_class_name = null
    rule = [{
      host = null
      http = [{
        path = [{
          backend = [{
            service_name = null
            service_port = null
          }]
          path = null
        }]
      }]
    }]
    tls = [{
      hosts       = []
      secret_name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "wait_for_load_balancer" {
  description = "(optional) - Terraform will wait for the load balancer to have at least 1 endpoint before considering the resource created."
  type        = bool
  default     = null
}

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
      backend = list(object(
        {
          service_name = string
          service_port = string
        }
      ))
      ingress_class_name = string
      rule = list(object(
        {
          host = string
          http = list(object(
            {
              path = list(object(
                {
                  backend = list(object(
                    {
                      service_name = string
                      service_port = string
                    }
                  ))
                  path = string
                }
              ))
            }
          ))
        }
      ))
      tls = list(object(
        {
          hosts       = list(string)
          secret_name = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_ingress" "this" {
  # wait_for_load_balancer - (optional) is a type of bool
  wait_for_load_balancer = var.wait_for_load_balancer

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
      # ingress_class_name - (optional) is a type of string
      ingress_class_name = spec.value["ingress_class_name"]

      dynamic "backend" {
        for_each = spec.value.backend
        content {
          # service_name - (optional) is a type of string
          service_name = backend.value["service_name"]
          # service_port - (optional) is a type of string
          service_port = backend.value["service_port"]
        }
      }

      dynamic "rule" {
        for_each = spec.value.rule
        content {
          # host - (optional) is a type of string
          host = rule.value["host"]

          dynamic "http" {
            for_each = rule.value.http
            content {

              dynamic "path" {
                for_each = http.value.path
                content {
                  # path - (optional) is a type of string
                  path = path.value["path"]

                  dynamic "backend" {
                    for_each = path.value.backend
                    content {
                      # service_name - (optional) is a type of string
                      service_name = backend.value["service_name"]
                      # service_port - (optional) is a type of string
                      service_port = backend.value["service_port"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "tls" {
        for_each = spec.value.tls
        content {
          # hosts - (optional) is a type of list of string
          hosts = tls.value["hosts"]
          # secret_name - (optional) is a type of string
          secret_name = tls.value["secret_name"]
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
  value       = kubernetes_ingress.this.id
}

output "status" {
  description = "returns a list of object"
  value       = kubernetes_ingress.this.status
}

output "this" {
  value = kubernetes_ingress.this
}
```

[top](#index)