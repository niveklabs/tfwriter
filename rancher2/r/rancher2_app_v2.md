# rancher2_app_v2

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
module "rancher2_app_v2" {
  source = "./modules/rancher2/r/rancher2_app_v2"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # chart_name - (required) is a type of string
  chart_name = null
  # chart_version - (optional) is a type of string
  chart_version = null
  # cleanup_on_fail - (optional) is a type of bool
  cleanup_on_fail = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # disable_hooks - (optional) is a type of bool
  disable_hooks = null
  # disable_open_api_validation - (optional) is a type of bool
  disable_open_api_validation = null
  # force_upgrade - (optional) is a type of bool
  force_upgrade = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # namespace - (required) is a type of string
  namespace = null
  # project_id - (optional) is a type of string
  project_id = null
  # repo_name - (required) is a type of string
  repo_name = null
  # values - (optional) is a type of string
  values = null
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

variable "chart_name" {
  description = "(required) - Chart name"
  type        = string
}

variable "chart_version" {
  description = "(optional) - Chart version"
  type        = string
  default     = null
}

variable "cleanup_on_fail" {
  description = "(optional) - Cleanup app V2 on failed chart upgrade"
  type        = bool
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "disable_hooks" {
  description = "(optional) - Disable app V2 chart hooks"
  type        = bool
  default     = null
}

variable "disable_open_api_validation" {
  description = "(optional) - Disable app V2 Open API Validation"
  type        = bool
  default     = null
}

variable "force_upgrade" {
  description = "(optional) - Force app V2 chart upgrade"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - App v2 name"
  type        = string
}

variable "namespace" {
  description = "(required) - App v2 namespace"
  type        = string
}

variable "project_id" {
  description = "(optional) - Deploy app within project ID"
  type        = string
  default     = null
}

variable "repo_name" {
  description = "(required) - Repo name"
  type        = string
}

variable "values" {
  description = "(optional) - App v2 custom values yaml"
  type        = string
  default     = null
}

variable "wait" {
  description = "(optional) - Wait until app is deployed"
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
resource "rancher2_app_v2" "this" {
  annotations                 = var.annotations
  chart_name                  = var.chart_name
  chart_version               = var.chart_version
  cleanup_on_fail             = var.cleanup_on_fail
  cluster_id                  = var.cluster_id
  disable_hooks               = var.disable_hooks
  disable_open_api_validation = var.disable_open_api_validation
  force_upgrade               = var.force_upgrade
  labels                      = var.labels
  name                        = var.name
  namespace                   = var.namespace
  project_id                  = var.project_id
  repo_name                   = var.repo_name
  values                      = var.values
  wait                        = var.wait

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
  value       = rancher2_app_v2.this.annotations
}

output "chart_version" {
  description = "returns a string"
  value       = rancher2_app_v2.this.chart_version
}

output "cluster_name" {
  description = "returns a string"
  value       = rancher2_app_v2.this.cluster_name
}

output "id" {
  description = "returns a string"
  value       = rancher2_app_v2.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_app_v2.this.labels
}

output "system_default_registry" {
  description = "returns a string"
  value       = rancher2_app_v2.this.system_default_registry
}

output "this" {
  value = rancher2_app_v2.this
}
```

[top](#index)