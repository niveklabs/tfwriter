# kubernetes_service

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "kubernetes_service" {
  source = "./modules/kubernetes/d/kubernetes_service"


  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    name             = null
    namespace        = null
    resource_version = null
    self_link        = null
    uid              = null
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
```

[top](#index)

### Datasource

```terraform
data "kubernetes_service" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      name        = metadata.value["name"]
      namespace   = metadata.value["namespace"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.kubernetes_service.this.id
}

output "spec" {
  description = "returns a list of object"
  value       = data.kubernetes_service.this.spec
}

output "status" {
  description = "returns a list of object"
  value       = data.kubernetes_service.this.status
}

output "this" {
  value = kubernetes_service.this
}
```

[top](#index)