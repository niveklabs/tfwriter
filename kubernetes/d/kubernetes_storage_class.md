# kubernetes_storage_class

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
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_storage_class" {
  source = "./modules/kubernetes/d/kubernetes_storage_class"


  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    name             = null
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
data "kubernetes_storage_class" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      name        = metadata.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_volume_expansion" {
  description = "returns a bool"
  value       = data.kubernetes_storage_class.this.allow_volume_expansion
}

output "id" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.id
}

output "mount_options" {
  description = "returns a set of string"
  value       = data.kubernetes_storage_class.this.mount_options
}

output "parameters" {
  description = "returns a map of string"
  value       = data.kubernetes_storage_class.this.parameters
}

output "reclaim_policy" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.reclaim_policy
}

output "storage_provisioner" {
  description = "returns a string"
  value       = data.kubernetes_storage_class.this.storage_provisioner
}

output "this" {
  value = kubernetes_storage_class.this
}
```

[top](#index)