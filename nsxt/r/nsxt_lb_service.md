# nsxt_lb_service

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
module "nsxt_lb_service" {
  source = "./modules/nsxt/r/nsxt_lb_service"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # error_log_level - (optional) is a type of string
  error_log_level = null
  # logical_router_id - (required) is a type of string
  logical_router_id = null
  # size - (optional) is a type of string
  size = null
  # virtual_server_ids - (optional) is a type of set of string
  virtual_server_ids = []

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Whether the load balancer service is enabled"
  type        = bool
  default     = null
}

variable "error_log_level" {
  description = "(optional) - Load balancer engine writes information about encountered issues of different severity levels to the error log. This setting is used to define the severity level of the error log"
  type        = string
  default     = null
}

variable "logical_router_id" {
  description = "(required) - Logical Tier1 Router to which the Load Balancer is to be attached"
  type        = string
}

variable "size" {
  description = "(optional) - Size of load balancer service"
  type        = string
  default     = null
}

variable "virtual_server_ids" {
  description = "(optional) - Virtual servers associated with this Load Balancer"
  type        = set(string)
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
resource "nsxt_lb_service" "this" {
  description        = var.description
  display_name       = var.display_name
  enabled            = var.enabled
  error_log_level    = var.error_log_level
  logical_router_id  = var.logical_router_id
  size               = var.size
  virtual_server_ids = var.virtual_server_ids

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_service.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_service.this.revision
}

output "this" {
  value = nsxt_lb_service.this
}
```

[top](#index)