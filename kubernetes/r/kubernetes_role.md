# kubernetes_role

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
module "kubernetes_role" {
  source = "./modules/kubernetes/r/kubernetes_role"


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

  rule = [{
    api_groups     = []
    resource_names = []
    resources      = []
    verbs          = []
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

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      api_groups     = set(string)
      resource_names = set(string)
      resources      = set(string)
      verbs          = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_role" "this" {

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

  dynamic "rule" {
    for_each = var.rule
    content {
      # api_groups - (required) is a type of set of string
      api_groups = rule.value["api_groups"]
      # resource_names - (optional) is a type of set of string
      resource_names = rule.value["resource_names"]
      # resources - (required) is a type of set of string
      resources = rule.value["resources"]
      # verbs - (required) is a type of set of string
      verbs = rule.value["verbs"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_role.this.id
}

output "this" {
  value = kubernetes_role.this
}
```

[top](#index)