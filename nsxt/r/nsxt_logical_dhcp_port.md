# nsxt_logical_dhcp_port

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
module "nsxt_logical_dhcp_port" {
  source = "./modules/nsxt/r/nsxt_logical_dhcp_port"

  # admin_state - (optional) is a type of string
  admin_state = null
  # description - (optional) is a type of string
  description = null
  # dhcp_server_id - (required) is a type of string
  dhcp_server_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # logical_switch_id - (required) is a type of string
  logical_switch_id = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_state" {
  description = "(optional) - Represents Desired state of the object"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "dhcp_server_id" {
  description = "(required) - Id of the Logical DHCP server this port belongs to"
  type        = string
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "logical_switch_id" {
  description = "(required) - Id of the Logical switch that this port belongs to"
  type        = string
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
resource "nsxt_logical_dhcp_port" "this" {
  admin_state       = var.admin_state
  description       = var.description
  dhcp_server_id    = var.dhcp_server_id
  display_name      = var.display_name
  logical_switch_id = var.logical_switch_id

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
  value       = nsxt_logical_dhcp_port.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_logical_dhcp_port.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_logical_dhcp_port.this.revision
}

output "this" {
  value = nsxt_logical_dhcp_port.this
}
```

[top](#index)