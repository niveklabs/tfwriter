# rancher2_certificate

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_certificate" {
  source = "./modules/rancher2/r/rancher2_certificate"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # certs - (required) is a type of string
  certs = null
  # description - (optional) is a type of string
  description = null
  # key - (required) is a type of string
  key = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # project_id - (required) is a type of string
  project_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "certs" {
  description = "(required) - Certificate certs base64 encoded"
  type        = string
}

variable "description" {
  description = "(optional) - Certificate description"
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - Certificate key base64 encoded"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - Certificate name"
  type        = string
  default     = null
}

variable "namespace_id" {
  description = "(optional) - Namespace ID to add certificate"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - Project ID to add certificate"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_certificate" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # certs - (required) is a type of string
  certs = var.certs
  # description - (optional) is a type of string
  description = var.description
  # key - (required) is a type of string
  key = var.key
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (optional) is a type of string
  name = var.name
  # namespace_id - (optional) is a type of string
  namespace_id = var.namespace_id
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_certificate.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_certificate.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_certificate.this.labels
}

output "this" {
  value = rancher2_certificate.this
}
```

[top](#index)