# rancher2_multi_cluster_app

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
module "rancher2_multi_cluster_app" {
  source = "./modules/rancher2/r/rancher2_multi_cluster_app"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # catalog_name - (required) is a type of string
  catalog_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # revision_history_limit - (optional) is a type of number
  revision_history_limit = null
  # revision_id - (optional) is a type of string
  revision_id = null
  # roles - (required) is a type of list of string
  roles = []
  # template_name - (required) is a type of string
  template_name = null
  # template_version - (optional) is a type of string
  template_version = null
  # wait - (optional) is a type of bool
  wait = null

  answers = [{
    cluster_id = null
    project_id = null
    values     = {}
  }]

  members = [{
    access_type        = null
    group_principal_id = null
    user_principal_id  = null
  }]

  targets = [{
    app_id       = null
    health_state = null
    project_id   = null
    state        = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  upgrade_strategy = [{
    rolling_update = [{
      batch_size = null
      interval   = null
    }]
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

variable "catalog_name" {
  description = "(required) - Multi cluster app catalog name"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Multi cluster app name"
  type        = string
}

variable "revision_history_limit" {
  description = "(optional) - Multi cluster app revision history limit"
  type        = number
  default     = null
}

variable "revision_id" {
  description = "(optional) - Multi cluster app revision name"
  type        = string
  default     = null
}

variable "roles" {
  description = "(required) - Multi cluster app roles"
  type        = list(string)
}

variable "template_name" {
  description = "(required) - Multi cluster app template name"
  type        = string
}

variable "template_version" {
  description = "(optional) - Multi cluster app template version"
  type        = string
  default     = null
}

variable "wait" {
  description = "(optional) - Wait until multi cluster app is active"
  type        = bool
  default     = null
}

variable "answers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cluster_id = string
      project_id = string
      values     = map(string)
    }
  ))
  default = []
}

variable "members" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_type        = string
      group_principal_id = string
      user_principal_id  = string
    }
  ))
  default = []
}

variable "targets" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      app_id       = string
      health_state = string
      project_id   = string
      state        = string
    }
  ))
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

variable "upgrade_strategy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      rolling_update = list(object(
        {
          batch_size = number
          interval   = number
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_multi_cluster_app" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # catalog_name - (required) is a type of string
  catalog_name = var.catalog_name
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # revision_history_limit - (optional) is a type of number
  revision_history_limit = var.revision_history_limit
  # revision_id - (optional) is a type of string
  revision_id = var.revision_id
  # roles - (required) is a type of list of string
  roles = var.roles
  # template_name - (required) is a type of string
  template_name = var.template_name
  # template_version - (optional) is a type of string
  template_version = var.template_version
  # wait - (optional) is a type of bool
  wait = var.wait

  dynamic "answers" {
    for_each = var.answers
    content {
      # cluster_id - (optional) is a type of string
      cluster_id = answers.value["cluster_id"]
      # project_id - (optional) is a type of string
      project_id = answers.value["project_id"]
      # values - (optional) is a type of map of string
      values = answers.value["values"]
    }
  }

  dynamic "members" {
    for_each = var.members
    content {
      # access_type - (optional) is a type of string
      access_type = members.value["access_type"]
      # group_principal_id - (optional) is a type of string
      group_principal_id = members.value["group_principal_id"]
      # user_principal_id - (optional) is a type of string
      user_principal_id = members.value["user_principal_id"]
    }
  }

  dynamic "targets" {
    for_each = var.targets
    content {
      # project_id - (required) is a type of string
      project_id = targets.value["project_id"]
    }
  }

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

  dynamic "upgrade_strategy" {
    for_each = var.upgrade_strategy
    content {

      dynamic "rolling_update" {
        for_each = upgrade_strategy.value.rolling_update
        content {
          # batch_size - (optional) is a type of number
          batch_size = rolling_update.value["batch_size"]
          # interval - (optional) is a type of number
          interval = rolling_update.value["interval"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_multi_cluster_app.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_multi_cluster_app.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_multi_cluster_app.this.labels
}

output "revision_id" {
  description = "returns a string"
  value       = rancher2_multi_cluster_app.this.revision_id
}

output "template_version" {
  description = "returns a string"
  value       = rancher2_multi_cluster_app.this.template_version
}

output "template_version_id" {
  description = "returns a string"
  value       = rancher2_multi_cluster_app.this.template_version_id
}

output "this" {
  value = rancher2_multi_cluster_app.this
}
```

[top](#index)