# rancher2_global_dns

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
module "rancher2_global_dns" {
  source = "./modules/rancher2/r/rancher2_global_dns"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # fqdn - (required) is a type of string
  fqdn = null
  # labels - (optional) is a type of map of string
  labels = {}
  # multi_cluster_app_id - (optional) is a type of string
  multi_cluster_app_id = null
  # name - (optional) is a type of string
  name = null
  # project_ids - (optional) is a type of list of string
  project_ids = []
  # provider_id - (required) is a type of string
  provider_id = null
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

variable "fqdn" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "multi_cluster_app_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "provider_id" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
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
resource "rancher2_global_dns" "this" {
  annotations          = var.annotations
  fqdn                 = var.fqdn
  labels               = var.labels
  multi_cluster_app_id = var.multi_cluster_app_id
  name                 = var.name
  project_ids          = var.project_ids
  provider_id          = var.provider_id
  ttl                  = var.ttl

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = rancher2_global_dns.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_global_dns.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_global_dns.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_global_dns.this.name
}

output "this" {
  value = rancher2_global_dns.this
}
```

[top](#index)