# nsxt_policy_dhcp_relay

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
module "nsxt_policy_dhcp_relay" {
  source = "./modules/nsxt/r/nsxt_policy_dhcp_relay"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # server_addresses - (required) is a type of list of string
  server_addresses = []

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
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "server_addresses" {
  description = "(required)"
  type        = list(string)
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
resource "nsxt_policy_dhcp_relay" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # server_addresses - (required) is a type of list of string
  server_addresses = var.server_addresses

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
output "id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_relay.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_relay.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_relay.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_dhcp_relay.this.revision
}

output "this" {
  value = nsxt_policy_dhcp_relay.this
}
```

[top](#index)