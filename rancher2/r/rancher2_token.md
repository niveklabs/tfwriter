# rancher2_token

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
module "rancher2_token" {
  source = "./modules/rancher2/r/rancher2_token"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (optional) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # renew - (optional) is a type of bool
  renew = null
  # ttl - (optional) is a type of number
  ttl = null

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

variable "cluster_id" {
  description = "(optional) - Cluster ID for scoped token"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Token description"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "renew" {
  description = "(optional) - Renew expired or disabled token"
  type        = bool
  default     = null
}

variable "ttl" {
  description = "(optional) - Token time to live in seconds"
  type        = number
  default     = null
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
resource "rancher2_token" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # renew - (optional) is a type of bool
  renew = var.renew
  # ttl - (optional) is a type of number
  ttl = var.ttl

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
output "access_key" {
  description = "returns a string"
  value       = rancher2_token.this.access_key
}

output "annotations" {
  description = "returns a map of string"
  value       = rancher2_token.this.annotations
}

output "enabled" {
  description = "returns a bool"
  value       = rancher2_token.this.enabled
}

output "expired" {
  description = "returns a bool"
  value       = rancher2_token.this.expired
}

output "id" {
  description = "returns a string"
  value       = rancher2_token.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_token.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_token.this.name
}

output "secret_key" {
  description = "returns a string"
  value       = rancher2_token.this.secret_key
  sensitive   = true
}

output "token" {
  description = "returns a string"
  value       = rancher2_token.this.token
  sensitive   = true
}

output "user_id" {
  description = "returns a string"
  value       = rancher2_token.this.user_id
}

output "this" {
  value = rancher2_token.this
}
```

[top](#index)