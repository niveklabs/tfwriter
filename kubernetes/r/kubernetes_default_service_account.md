# kubernetes_default_service_account

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
module "kubernetes_default_service_account" {
  source = "./modules/kubernetes/r/kubernetes_default_service_account"

  # automount_service_account_token - (optional) is a type of bool
  automount_service_account_token = null

  image_pull_secret = [{
    name = null
  }]

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

  secret = [{
    name = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "automount_service_account_token" {
  description = "(optional) - Enable automatic mounting of the service account token"
  type        = bool
  default     = null
}

variable "image_pull_secret" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

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

variable "secret" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_default_service_account" "this" {
  automount_service_account_token = var.automount_service_account_token

  dynamic "image_pull_secret" {
    for_each = var.image_pull_secret
    content {
      name = image_pull_secret.value["name"]
    }
  }

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      name        = metadata.value["name"]
      namespace   = metadata.value["namespace"]
    }
  }

  dynamic "secret" {
    for_each = var.secret
    content {
      name = secret.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_secret_name" {
  description = "returns a string"
  value       = kubernetes_default_service_account.this.default_secret_name
}

output "id" {
  description = "returns a string"
  value       = kubernetes_default_service_account.this.id
}

output "this" {
  value = kubernetes_default_service_account.this
}
```

[top](#index)