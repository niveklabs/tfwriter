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
    kubernetes = ">= 1.13.3"
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

variable "rule" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
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
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
      namespace     = metadata.value["namespace"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {
      api_groups     = rule.value["api_groups"]
      resource_names = rule.value["resource_names"]
      resources      = rule.value["resources"]
      verbs          = rule.value["verbs"]
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