# kubernetes_service_account

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
module "kubernetes_service_account" {
  source = "./modules/kubernetes/d/kubernetes_service_account"


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
data "kubernetes_service_account" "this" {

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
output "automount_service_account_token" {
  description = "returns a bool"
  value       = data.kubernetes_service_account.this.automount_service_account_token
}

output "default_secret_name" {
  description = "returns a string"
  value       = data.kubernetes_service_account.this.default_secret_name
}

output "id" {
  description = "returns a string"
  value       = data.kubernetes_service_account.this.id
}

output "image_pull_secret" {
  description = "returns a list of object"
  value       = data.kubernetes_service_account.this.image_pull_secret
}

output "secret" {
  description = "returns a list of object"
  value       = data.kubernetes_service_account.this.secret
}

output "this" {
  value = kubernetes_service_account.this
}
```

[top](#index)