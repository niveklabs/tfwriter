# rancher2_app

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
module "rancher2_app" {
  source = "./modules/rancher2/r/rancher2_app"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # answers - (optional) is a type of map of string
  answers = {}
  # catalog_name - (required) is a type of string
  catalog_name = null
  # description - (optional) is a type of string
  description = null
  # force_upgrade - (optional) is a type of bool
  force_upgrade = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # revision_id - (optional) is a type of string
  revision_id = null
  # target_namespace - (required) is a type of string
  target_namespace = null
  # template_name - (required) is a type of string
  template_name = null
  # template_version - (optional) is a type of string
  template_version = null
  # values_yaml - (optional) is a type of string
  values_yaml = null
  # wait - (optional) is a type of bool
  wait = null

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

variable "answers" {
  description = "(optional) - Answers of the app"
  type        = map(string)
  default     = null
}

variable "catalog_name" {
  description = "(required) - Catalog name of the app"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_upgrade" {
  description = "(optional) - Force app upgrade"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the app"
  type        = string
}

variable "project_id" {
  description = "(required) - Project ID to add app"
  type        = string
}

variable "revision_id" {
  description = "(optional) - App revision id"
  type        = string
  default     = null
}

variable "target_namespace" {
  description = "(required) - Namespace name to add app"
  type        = string
}

variable "template_name" {
  description = "(required) - Template name of the app"
  type        = string
}

variable "template_version" {
  description = "(optional) - Template version of the app"
  type        = string
  default     = null
}

variable "values_yaml" {
  description = "(optional) - values.yaml base64 encoded file content of the app"
  type        = string
  default     = null
}

variable "wait" {
  description = "(optional) - Wait until app is deployed and active"
  type        = bool
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
resource "rancher2_app" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # answers - (optional) is a type of map of string
  answers = var.answers
  # catalog_name - (required) is a type of string
  catalog_name = var.catalog_name
  # description - (optional) is a type of string
  description = var.description
  # force_upgrade - (optional) is a type of bool
  force_upgrade = var.force_upgrade
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # revision_id - (optional) is a type of string
  revision_id = var.revision_id
  # target_namespace - (required) is a type of string
  target_namespace = var.target_namespace
  # template_name - (required) is a type of string
  template_name = var.template_name
  # template_version - (optional) is a type of string
  template_version = var.template_version
  # values_yaml - (optional) is a type of string
  values_yaml = var.values_yaml
  # wait - (optional) is a type of bool
  wait = var.wait

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
  value       = rancher2_app.this.annotations
}

output "description" {
  description = "returns a string"
  value       = rancher2_app.this.description
}

output "external_id" {
  description = "returns a string"
  value       = rancher2_app.this.external_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_app.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_app.this.labels
}

output "revision_id" {
  description = "returns a string"
  value       = rancher2_app.this.revision_id
}

output "template_version" {
  description = "returns a string"
  value       = rancher2_app.this.template_version
}

output "this" {
  value = rancher2_app.this
}
```

[top](#index)