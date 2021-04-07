# kubernetes_role_binding

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
module "kubernetes_role_binding" {
  source = "./modules/kubernetes/r/kubernetes_role_binding"


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

variable "role_ref" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      api_group = string
      kind      = string
      name      = string
    }
  ))
}

variable "subject" {
  description = "nested block: NestingList, min items: 1, max items: 0"
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
resource "kubernetes_role_binding" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # annotations - (optional) is a type of map of string
      annotations = metadata.value["annotations"]
      # labels - (optional) is a type of map of string
      labels = metadata.value["labels"]
      # name - (optional) is a type of string
      name = metadata.value["name"]
      # namespace - (optional) is a type of string
      namespace = metadata.value["namespace"]
    }
  }

  dynamic "role_ref" {
    for_each = var.role_ref
    content {
      # api_group - (required) is a type of string
      api_group = role_ref.value["api_group"]
      # kind - (required) is a type of string
      kind = role_ref.value["kind"]
      # name - (required) is a type of string
      name = role_ref.value["name"]
    }
  }

  dynamic "subject" {
    for_each = var.subject
    content {
      # api_group - (optional) is a type of string
      api_group = subject.value["api_group"]
      # kind - (required) is a type of string
      kind = subject.value["kind"]
      # name - (required) is a type of string
      name = subject.value["name"]
      # namespace - (optional) is a type of string
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
  value       = kubernetes_role_binding.this.id
}

output "this" {
  value = kubernetes_role_binding.this
}
```

[top](#index)