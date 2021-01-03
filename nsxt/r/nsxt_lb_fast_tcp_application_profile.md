# nsxt_lb_fast_tcp_application_profile

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
module "nsxt_lb_fast_tcp_application_profile" {
  source = "./modules/nsxt/r/nsxt_lb_fast_tcp_application_profile"

  # close_timeout - (optional) is a type of number
  close_timeout = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # ha_flow_mirroring - (optional) is a type of bool
  ha_flow_mirroring = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "close_timeout" {
  description = "(optional) - Timeout in seconds to specify how long a closed TCP connection should be kept for this application before cleaning up the connection"
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

variable "ha_flow_mirroring" {
  description = "(optional) - A boolean flag which reflects whether flow mirroring is enabled, and all the flows to the bounded virtual server are mirrored to the standby node"
  type        = bool
  default     = null
}

variable "idle_timeout" {
  description = "(optional) - Timeout in seconds to specify how long an idle TCP connection in ESTABLISHED state should be kept for this application before cleaning up"
  type        = number
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
resource "nsxt_lb_fast_tcp_application_profile" "this" {
  close_timeout     = var.close_timeout
  description       = var.description
  display_name      = var.display_name
  ha_flow_mirroring = var.ha_flow_mirroring
  idle_timeout      = var.idle_timeout

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
  value       = nsxt_lb_fast_tcp_application_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_fast_tcp_application_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_fast_tcp_application_profile.this.revision
}

output "this" {
  value = nsxt_lb_fast_tcp_application_profile.this
}
```

[top](#index)