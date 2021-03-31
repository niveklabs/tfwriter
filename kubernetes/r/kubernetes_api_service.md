# kubernetes_api_service

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
module "kubernetes_api_service" {
  source = "./modules/kubernetes/r/kubernetes_api_service"


  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    ca_bundle                = null
    group                    = null
    group_priority_minimum   = null
    insecure_skip_tls_verify = null
    service = [{
      name      = null
      namespace = null
      port      = null
    }]
    version          = null
    version_priority = null
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
      ca_bundle                = string
      group                    = string
      group_priority_minimum   = number
      insecure_skip_tls_verify = bool
      service = list(object(
        {
          name      = string
          namespace = string
          port      = number
        }
      ))
      version          = string
      version_priority = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_api_service" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      ca_bundle                = spec.value["ca_bundle"]
      group                    = spec.value["group"]
      group_priority_minimum   = spec.value["group_priority_minimum"]
      insecure_skip_tls_verify = spec.value["insecure_skip_tls_verify"]
      version                  = spec.value["version"]
      version_priority         = spec.value["version_priority"]

      dynamic "service" {
        for_each = spec.value.service
        content {
          name      = service.value["name"]
          namespace = service.value["namespace"]
          port      = service.value["port"]
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
  value       = kubernetes_api_service.this.id
}

output "this" {
  value = kubernetes_api_service.this
}
```

[top](#index)