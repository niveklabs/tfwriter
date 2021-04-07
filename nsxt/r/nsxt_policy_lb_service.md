# nsxt_policy_lb_service

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_lb_service" {
  source = "./modules/nsxt/r/nsxt_policy_lb_service"

  # connectivity_path - (optional) is a type of string
  connectivity_path = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # error_log_level - (optional) is a type of string
  error_log_level = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # size - (optional) is a type of string
  size = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connectivity_path" {
  description = "(optional) - Policy path for connected policy object"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "enabled" {
  description = "(optional) - Flag to enable the Service"
  type        = bool
  default     = null
}

variable "error_log_level" {
  description = "(optional) - Log level for Load Balancer Service messages"
  type        = string
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional) - Load Balancer Service size"
  type        = string
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_lb_service" "this" {
  # connectivity_path - (optional) is a type of string
  connectivity_path = var.connectivity_path
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # error_log_level - (optional) is a type of string
  error_log_level = var.error_log_level
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # size - (optional) is a type of string
  size = var.size

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_lb_service.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_lb_service.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_lb_service.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_lb_service.this.revision
}

output "this" {
  value = nsxt_policy_lb_service.this
}
```

[top](#index)