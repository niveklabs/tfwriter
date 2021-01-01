# kubernetes_secret

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "kubernetes_secret" {
  source = "./modules/kubernetes/d/kubernetes_secret"


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

```hcl
variable "metadata" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
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

```hcl
data "kubernetes_secret" "this" {

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

```hcl
output "data" {
  description = "returns a map of string"
  value       = data.kubernetes_secret.this.data
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.kubernetes_secret.this.id
}

output "type" {
  description = "returns a string"
  value       = data.kubernetes_secret.this.type
}

output "this" {
  value = kubernetes_secret.this
}
```

[top](#index)