# nsxt_dhcp_server_ip_pool

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
module "nsxt_dhcp_server_ip_pool" {
  source = "./modules/nsxt/r/nsxt_dhcp_server_ip_pool"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # error_threshold - (optional) is a type of number
  error_threshold = null
  # gateway_ip - (optional) is a type of string
  gateway_ip = null
  # lease_time - (optional) is a type of number
  lease_time = null
  # logical_dhcp_server_id - (required) is a type of string
  logical_dhcp_server_id = null
  # warning_threshold - (optional) is a type of number
  warning_threshold = null

  dhcp_generic_option = [{
    code   = null
    values = []
  }]

  dhcp_option_121 = [{
    network  = null
    next_hop = null
  }]

  ip_range = [{
    end   = null
    start = null
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

variable "error_threshold" {
  description = "(optional) - Error threshold"
  type        = number
  default     = null
}

variable "gateway_ip" {
  description = "(optional) - Gateway ip"
  type        = string
  default     = null
}

variable "lease_time" {
  description = "(optional) - Lease time, in seconds"
  type        = number
  default     = null
}

variable "logical_dhcp_server_id" {
  description = "(required) - Id of dhcp server this pool is serving"
  type        = string
}

variable "warning_threshold" {
  description = "(optional) - Warning threshold"
  type        = number
  default     = null
}

variable "dhcp_generic_option" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      code   = number
      values = list(string)
    }
  ))
  default = []
}

variable "dhcp_option_121" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      network  = string
      next_hop = string
    }
  ))
  default = []
}

variable "ip_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end   = string
      start = string
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
resource "nsxt_dhcp_server_ip_pool" "this" {
  description            = var.description
  display_name           = var.display_name
  error_threshold        = var.error_threshold
  gateway_ip             = var.gateway_ip
  lease_time             = var.lease_time
  logical_dhcp_server_id = var.logical_dhcp_server_id
  warning_threshold      = var.warning_threshold

  dynamic "dhcp_generic_option" {
    for_each = var.dhcp_generic_option
    content {
      code   = dhcp_generic_option.value["code"]
      values = dhcp_generic_option.value["values"]
    }
  }

  dynamic "dhcp_option_121" {
    for_each = var.dhcp_option_121
    content {
      network  = dhcp_option_121.value["network"]
      next_hop = dhcp_option_121.value["next_hop"]
    }
  }

  dynamic "ip_range" {
    for_each = var.ip_range
    content {
      end   = ip_range.value["end"]
      start = ip_range.value["start"]
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
  value       = nsxt_dhcp_server_ip_pool.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_dhcp_server_ip_pool.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_dhcp_server_ip_pool.this.revision
}

output "this" {
  value = nsxt_dhcp_server_ip_pool.this
}
```

[top](#index)