# kubernetes_certificate_signing_request

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
module "kubernetes_certificate_signing_request" {
  source = "./modules/kubernetes/r/kubernetes_certificate_signing_request"

  # auto_approve - (optional) is a type of bool
  auto_approve = null

  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    request     = null
    signer_name = null
    usages      = []
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_approve" {
  description = "(optional) - Automatically approve the CertificateSigningRequest"
  type        = bool
  default     = null
}

variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generate_name    = string
      generation       = number
      labels           = map(string)
      name             = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      request     = string
      signer_name = string
      usages      = set(string)
    }
  ))
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
resource "kubernetes_certificate_signing_request" "this" {
  # auto_approve - (optional) is a type of bool
  auto_approve = var.auto_approve

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
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      # request - (required) is a type of string
      request = spec.value["request"]
      # signer_name - (optional) is a type of string
      signer_name = spec.value["signer_name"]
      # usages - (optional) is a type of set of string
      usages = spec.value["usages"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = kubernetes_certificate_signing_request.this.certificate
}

output "id" {
  description = "returns a string"
  value       = kubernetes_certificate_signing_request.this.id
}

output "this" {
  value = kubernetes_certificate_signing_request.this
}
```

[top](#index)