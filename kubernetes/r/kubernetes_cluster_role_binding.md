# kubernetes_cluster_role_binding

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
module "kubernetes_cluster_role_binding" {
  source = "./modules/kubernetes/r/kubernetes_cluster_role_binding"


  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  role_ref = [{
    api_group = null
    kind      = null
    name      = null
  }]

  subject = [{
    api_group = null
    kind      = null
    name      = null
    namespace = null
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
      generation       = number
      labels           = map(string)
      name             = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "role_ref" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      api_group = string
      kind      = string
      name      = string
    }
  ))
}

variable "subject" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      api_group = string
      kind      = string
      name      = string
      namespace = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_cluster_role_binding" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      name        = metadata.value["name"]
    }
  }

  dynamic "role_ref" {
    for_each = var.role_ref
    content {
      api_group = role_ref.value["api_group"]
      kind      = role_ref.value["kind"]
      name      = role_ref.value["name"]
    }
  }

  dynamic "subject" {
    for_each = var.subject
    content {
      api_group = subject.value["api_group"]
      kind      = subject.value["kind"]
      name      = subject.value["name"]
      namespace = subject.value["namespace"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_cluster_role_binding.this.id
}

output "this" {
  value = kubernetes_cluster_role_binding.this
}
```

[top](#index)