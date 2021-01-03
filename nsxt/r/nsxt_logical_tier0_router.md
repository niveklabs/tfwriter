# nsxt_logical_tier0_router

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
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_logical_tier0_router" {
  source = "./modules/nsxt/r/nsxt_logical_tier0_router"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_id - (required) is a type of string
  edge_cluster_id = null
  # failover_mode - (optional) is a type of string
  failover_mode = null
  # high_availability_mode - (optional) is a type of string
  high_availability_mode = null

  firewall_sections = [{
    is_valid            = null
    target_display_name = null
    target_id           = null
    target_type         = null
  }]

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

variable "edge_cluster_id" {
  description = "(required) - Edge Cluster Id"
  type        = string
}

variable "failover_mode" {
  description = "(optional) - Failover mode which determines whether the preferred service router instance for given logical router will preempt the peer"
  type        = string
  default     = null
}

variable "high_availability_mode" {
  description = "(optional) - High availability mode"
  type        = string
  default     = null
}

variable "firewall_sections" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_valid            = bool
      target_display_name = string
      target_id           = string
      target_type         = string
    }
  ))
  default = []
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
resource "nsxt_logical_tier0_router" "this" {
  description            = var.description
  display_name           = var.display_name
  edge_cluster_id        = var.edge_cluster_id
  failover_mode          = var.failover_mode
  high_availability_mode = var.high_availability_mode

  dynamic "firewall_sections" {
    for_each = var.firewall_sections
    content {
      target_id   = firewall_sections.value["target_id"]
      target_type = firewall_sections.value["target_type"]
    }
  }

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
  value       = nsxt_logical_tier0_router.this.display_name
}

output "failover_mode" {
  description = "returns a string"
  value       = nsxt_logical_tier0_router.this.failover_mode
}

output "id" {
  description = "returns a string"
  value       = nsxt_logical_tier0_router.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_logical_tier0_router.this.revision
}

output "this" {
  value = nsxt_logical_tier0_router.this
}
```

[top](#index)