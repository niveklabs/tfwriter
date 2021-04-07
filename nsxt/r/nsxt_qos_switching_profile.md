# nsxt_qos_switching_profile

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
module "nsxt_qos_switching_profile" {
  source = "./modules/nsxt/r/nsxt_qos_switching_profile"

  # class_of_service - (optional) is a type of number
  class_of_service = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # dscp_priority - (optional) is a type of number
  dscp_priority = null
  # dscp_trusted - (optional) is a type of bool
  dscp_trusted = null

  egress_rate_shaper = [{
    average_bw_mbps = null
    burst_size      = null
    enabled         = null
    peak_bw_mbps    = null
  }]

  ingress_broadcast_rate_shaper = [{
    average_bw_kbps = null
    burst_size      = null
    enabled         = null
    peak_bw_kbps    = null
  }]

  ingress_rate_shaper = [{
    average_bw_mbps = null
    burst_size      = null
    enabled         = null
    peak_bw_mbps    = null
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
variable "class_of_service" {
  description = "(optional) - Class of service"
  type        = number
  default     = null
}

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

variable "dscp_priority" {
  description = "(optional) - DSCP Priority"
  type        = number
  default     = null
}

variable "dscp_trusted" {
  description = "(optional) - Trust mode for DSCP"
  type        = bool
  default     = null
}

variable "egress_rate_shaper" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      average_bw_mbps = number
      burst_size      = number
      enabled         = bool
      peak_bw_mbps    = number
    }
  ))
  default = []
}

variable "ingress_broadcast_rate_shaper" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      average_bw_kbps = number
      burst_size      = number
      enabled         = bool
      peak_bw_kbps    = number
    }
  ))
  default = []
}

variable "ingress_rate_shaper" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      average_bw_mbps = number
      burst_size      = number
      enabled         = bool
      peak_bw_mbps    = number
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
resource "nsxt_qos_switching_profile" "this" {
  # class_of_service - (optional) is a type of number
  class_of_service = var.class_of_service
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # dscp_priority - (optional) is a type of number
  dscp_priority = var.dscp_priority
  # dscp_trusted - (optional) is a type of bool
  dscp_trusted = var.dscp_trusted

  dynamic "egress_rate_shaper" {
    for_each = var.egress_rate_shaper
    content {
      # average_bw_mbps - (optional) is a type of number
      average_bw_mbps = egress_rate_shaper.value["average_bw_mbps"]
      # burst_size - (optional) is a type of number
      burst_size = egress_rate_shaper.value["burst_size"]
      # enabled - (optional) is a type of bool
      enabled = egress_rate_shaper.value["enabled"]
      # peak_bw_mbps - (optional) is a type of number
      peak_bw_mbps = egress_rate_shaper.value["peak_bw_mbps"]
    }
  }

  dynamic "ingress_broadcast_rate_shaper" {
    for_each = var.ingress_broadcast_rate_shaper
    content {
      # average_bw_kbps - (optional) is a type of number
      average_bw_kbps = ingress_broadcast_rate_shaper.value["average_bw_kbps"]
      # burst_size - (optional) is a type of number
      burst_size = ingress_broadcast_rate_shaper.value["burst_size"]
      # enabled - (optional) is a type of bool
      enabled = ingress_broadcast_rate_shaper.value["enabled"]
      # peak_bw_kbps - (optional) is a type of number
      peak_bw_kbps = ingress_broadcast_rate_shaper.value["peak_bw_kbps"]
    }
  }

  dynamic "ingress_rate_shaper" {
    for_each = var.ingress_rate_shaper
    content {
      # average_bw_mbps - (optional) is a type of number
      average_bw_mbps = ingress_rate_shaper.value["average_bw_mbps"]
      # burst_size - (optional) is a type of number
      burst_size = ingress_rate_shaper.value["burst_size"]
      # enabled - (optional) is a type of bool
      enabled = ingress_rate_shaper.value["enabled"]
      # peak_bw_mbps - (optional) is a type of number
      peak_bw_mbps = ingress_rate_shaper.value["peak_bw_mbps"]
    }
  }

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
  value       = nsxt_qos_switching_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_qos_switching_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_qos_switching_profile.this.revision
}

output "this" {
  value = nsxt_qos_switching_profile.this
}
```

[top](#index)