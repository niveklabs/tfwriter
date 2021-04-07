# nsxt_lb_passive_monitor

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
module "nsxt_lb_passive_monitor" {
  source = "./modules/nsxt/r/nsxt_lb_passive_monitor"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # max_fails - (optional) is a type of number
  max_fails = null
  # timeout - (optional) is a type of number
  timeout = null

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

variable "max_fails" {
  description = "(optional) - When the consecutive failures reach this value, then the member is considered temporarily unavailable for a configurable period"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional) - After this timeout period, the member is tried again for a new connection to see if it is available"
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
resource "nsxt_lb_passive_monitor" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # max_fails - (optional) is a type of number
  max_fails = var.max_fails
  # timeout - (optional) is a type of number
  timeout = var.timeout

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
  value       = nsxt_lb_passive_monitor.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_passive_monitor.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_passive_monitor.this.revision
}

output "this" {
  value = nsxt_lb_passive_monitor.this
}
```

[top](#index)