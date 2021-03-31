# nsxt_policy_gateway_dns_forwarder

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
module "nsxt_policy_gateway_dns_forwarder" {
  source = "./modules/nsxt/r/nsxt_policy_gateway_dns_forwarder"

  # conditional_forwarder_zone_paths - (optional) is a type of list of string
  conditional_forwarder_zone_paths = []
  # default_forwarder_zone_path - (required) is a type of string
  default_forwarder_zone_path = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # gateway_path - (required) is a type of string
  gateway_path = null
  # listener_ip - (required) is a type of string
  listener_ip = null
  # log_level - (optional) is a type of string
  log_level = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "conditional_forwarder_zone_paths" {
  description = "(optional) - List of conditional (FQDN) forwarder zone paths"
  type        = list(string)
  default     = null
}

variable "default_forwarder_zone_path" {
  description = "(required) - Zone to which DNS requests are forwarded by default"
  type        = string
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
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gateway_path" {
  description = "(required) - Policy path for the Gateway"
  type        = string
}

variable "listener_ip" {
  description = "(required) - IP on which the DNS Forwarder listens"
  type        = string
}

variable "log_level" {
  description = "(optional) - Log level"
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
resource "nsxt_policy_gateway_dns_forwarder" "this" {
  conditional_forwarder_zone_paths = var.conditional_forwarder_zone_paths
  default_forwarder_zone_path      = var.default_forwarder_zone_path
  description                      = var.description
  display_name                     = var.display_name
  enabled                          = var.enabled
  gateway_path                     = var.gateway_path
  listener_ip                      = var.listener_ip
  log_level                        = var.log_level

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
output "id" {
  description = "returns a string"
  value       = nsxt_policy_gateway_dns_forwarder.this.id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_gateway_dns_forwarder.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_gateway_dns_forwarder.this.revision
}

output "this" {
  value = nsxt_policy_gateway_dns_forwarder.this
}
```

[top](#index)