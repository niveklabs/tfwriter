# kubernetes_persistent_volume_claim

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
module "kubernetes_persistent_volume_claim" {
  source = "./modules/kubernetes/d/kubernetes_persistent_volume_claim"


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
    access_modes = []
    resources = [{
      limits   = {}
      requests = {}
    }]
    selector = [{
      match_expressions = [{
        key      = null
        operator = null
        values   = []
      }]
      match_labels = {}
    }]
    storage_class_name = null
    volume_name        = null
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
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_modes = set(string)
      resources = list(object(
        {
          limits   = map(string)
          requests = map(string)
        }
      ))
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
      storage_class_name = string
      volume_name        = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "kubernetes_persistent_volume_claim" "this" {

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
      # storage_class_name - (optional) is a type of string
      storage_class_name = spec.value["storage_class_name"]
      # volume_name - (optional) is a type of string
      volume_name = spec.value["volume_name"]

      dynamic "selector" {
        for_each = spec.value.selector
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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.kubernetes_persistent_volume_claim.this.id
}

output "this" {
  value = kubernetes_persistent_volume_claim.this
}
```

[top](#index)