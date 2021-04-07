# nsxt_logical_router_centralized_service_port

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
module "nsxt_logical_router_centralized_service_port" {
  source = "./modules/nsxt/r/nsxt_logical_router_centralized_service_port"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # ip_address - (required) is a type of string
  ip_address = null
  # linked_logical_switch_port_id - (required) is a type of string
  linked_logical_switch_port_id = null
  # logical_router_id - (required) is a type of string
  logical_router_id = null
  # urpf_mode - (optional) is a type of string
  urpf_mode = null

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

variable "ip_address" {
  description = "(required) - Logical router port subnet (ipAddress / prefix length)"
  type        = string
}

variable "linked_logical_switch_port_id" {
  description = "(required) - Identifier for port on logical switch to connect to"
  type        = string
}

variable "logical_router_id" {
  description = "(required) - Identifier for logical router on which this port is created"
  type        = string
}

variable "urpf_mode" {
  description = "(optional) - Unicast Reverse Path Forwarding mode"
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
resource "nsxt_logical_router_centralized_service_port" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # ip_address - (required) is a type of string
  ip_address = var.ip_address
  # linked_logical_switch_port_id - (required) is a type of string
  linked_logical_switch_port_id = var.linked_logical_switch_port_id
  # logical_router_id - (required) is a type of string
  logical_router_id = var.logical_router_id
  # urpf_mode - (optional) is a type of string
  urpf_mode = var.urpf_mode

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
output "display_name" {
  description = "returns a string"
  value       = nsxt_logical_router_centralized_service_port.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_logical_router_centralized_service_port.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_logical_router_centralized_service_port.this.revision
}

output "this" {
  value = nsxt_logical_router_centralized_service_port.this
}
```

[top](#index)