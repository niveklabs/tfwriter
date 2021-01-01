# kubernetes_ingress

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

```hcl
variable "wait_for_load_balancer" {
  description = "(optional) - Terraform will wait for the load balancer to have at least 1 endpoint before considering the resource created."
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
      backend = list(object(
        {
          service_name = string
          service_port = string
        }
      ))
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

```hcl
resource "kubernetes_ingress" "this" {
  wait_for_load_balancer = var.wait_for_load_balancer

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

      dynamic "backend" {
        for_each = spec.value.backend
        content {
          service_name = backend.value["service_name"]
          service_port = backend.value["service_port"]
        }
      }

      dynamic "rule" {
        for_each = spec.value.rule
        content {
          host = rule.value["host"]

          dynamic "http" {
            for_each = rule.value.http
            content {

              dynamic "path" {
                for_each = http.value.path
                content {
                  path = path.value["path"]

                  dynamic "backend" {
                    for_each = path.value.backend
                    content {
                      service_name = backend.value["service_name"]
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
          hosts       = tls.value["hosts"]
          secret_name = tls.value["secret_name"]
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
  value       = kubernetes_ingress.this.id
}

output "load_balancer_ingress" {
  description = "returns a list of object"
  value       = kubernetes_ingress.this.load_balancer_ingress
}

output "this" {
  value = kubernetes_ingress.this
}
```

[top](#index)