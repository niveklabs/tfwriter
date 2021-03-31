# avi_poolgroup

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_poolgroup" {
  source = "./modules/avi/r/avi_poolgroup"

  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = null
  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # created_by - (optional) is a type of string
  created_by = null
  # deployment_policy_ref - (optional) is a type of string
  deployment_policy_ref = null
  # description - (optional) is a type of string
  description = null
  # implicit_priority_labels - (optional) is a type of bool
  implicit_priority_labels = null
  # min_servers - (optional) is a type of number
  min_servers = null
  # name - (required) is a type of string
  name = null
  # priority_labels_ref - (optional) is a type of string
  priority_labels_ref = null
  # service_metadata - (optional) is a type of string
  service_metadata = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  fail_action = [{
    local_rsp = [{
      file = [{
        content_type = null
        file_content = null
      }]
      status_code = null
    }]
    redirect = [{
      host        = null
      path        = null
      protocol    = null
      query       = null
      status_code = null
    }]
    type = null
  }]

  members = [{
    deployment_state = null
    pool_ref         = null
    priority_label   = null
    ratio            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_config_cksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_policy_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "implicit_priority_labels" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "min_servers" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority_labels_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fail_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      local_rsp = set(object(
        {
          file = set(object(
            {
              content_type = string
              file_content = string
            }
          ))
          status_code = string
        }
      ))
      redirect = set(object(
        {
          host        = string
          path        = string
          protocol    = string
          query       = string
          status_code = string
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "members" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      deployment_state = string
      pool_ref         = string
      priority_label   = string
      ratio            = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_poolgroup" "this" {
  cloud_config_cksum       = var.cloud_config_cksum
  cloud_ref                = var.cloud_ref
  created_by               = var.created_by
  deployment_policy_ref    = var.deployment_policy_ref
  description              = var.description
  implicit_priority_labels = var.implicit_priority_labels
  min_servers              = var.min_servers
  name                     = var.name
  priority_labels_ref      = var.priority_labels_ref
  service_metadata         = var.service_metadata
  tenant_ref               = var.tenant_ref
  uuid                     = var.uuid

  dynamic "fail_action" {
    for_each = var.fail_action
    content {
      type = fail_action.value["type"]

      dynamic "local_rsp" {
        for_each = fail_action.value.local_rsp
        content {
          status_code = local_rsp.value["status_code"]

          dynamic "file" {
            for_each = local_rsp.value.file
            content {
              content_type = file.value["content_type"]
              file_content = file.value["file_content"]
            }
          }

        }
      }

      dynamic "redirect" {
        for_each = fail_action.value.redirect
        content {
          host        = redirect.value["host"]
          path        = redirect.value["path"]
          protocol    = redirect.value["protocol"]
          query       = redirect.value["query"]
          status_code = redirect.value["status_code"]
        }
      }

    }
  }

  dynamic "members" {
    for_each = var.members
    content {
      deployment_state = members.value["deployment_state"]
      pool_ref         = members.value["pool_ref"]
      priority_label   = members.value["priority_label"]
      ratio            = members.value["ratio"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_config_cksum" {
  description = "returns a string"
  value       = avi_poolgroup.this.cloud_config_cksum
}

output "cloud_ref" {
  description = "returns a string"
  value       = avi_poolgroup.this.cloud_ref
}

output "created_by" {
  description = "returns a string"
  value       = avi_poolgroup.this.created_by
}

output "deployment_policy_ref" {
  description = "returns a string"
  value       = avi_poolgroup.this.deployment_policy_ref
}

output "description" {
  description = "returns a string"
  value       = avi_poolgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_poolgroup.this.id
}

output "priority_labels_ref" {
  description = "returns a string"
  value       = avi_poolgroup.this.priority_labels_ref
}

output "service_metadata" {
  description = "returns a string"
  value       = avi_poolgroup.this.service_metadata
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_poolgroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_poolgroup.this.uuid
}

output "this" {
  value = avi_poolgroup.this
}
```

[top](#index)