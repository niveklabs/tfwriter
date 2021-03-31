# nsxt_logical_router_link_port_on_tier0

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
module "nsxt_logical_router_link_port_on_tier0" {
  source = "./modules/nsxt/r/nsxt_logical_router_link_port_on_tier0"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # logical_router_id - (required) is a type of string
  logical_router_id = null

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

variable "logical_router_id" {
  description = "(required) - Identifier for logical router on which this port is created"
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
resource "nsxt_logical_router_link_port_on_tier0" "this" {
  description       = var.description
  display_name      = var.display_name
  logical_router_id = var.logical_router_id

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
  value       = nsxt_logical_router_link_port_on_tier0.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_logical_router_link_port_on_tier0.this.id
}

output "linked_logical_router_port_id" {
  description = "returns a string"
  value       = nsxt_logical_router_link_port_on_tier0.this.linked_logical_router_port_id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_logical_router_link_port_on_tier0.this.revision
}

output "this" {
  value = nsxt_logical_router_link_port_on_tier0.this
}
```

[top](#index)