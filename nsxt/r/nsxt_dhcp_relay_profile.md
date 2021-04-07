# nsxt_dhcp_relay_profile

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
module "nsxt_dhcp_relay_profile" {
  source = "./modules/nsxt/r/nsxt_dhcp_relay_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # server_addresses - (required) is a type of set of string
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
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "server_addresses" {
  description = "(required) - Set of dhcp relay server addresses"
  type        = set(string)
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
resource "nsxt_dhcp_relay_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # server_addresses - (required) is a type of set of string
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
output "display_name" {
  description = "returns a string"
  value       = nsxt_dhcp_relay_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_dhcp_relay_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_dhcp_relay_profile.this.revision
}

output "this" {
  value = nsxt_dhcp_relay_profile.this
}
```

[top](#index)