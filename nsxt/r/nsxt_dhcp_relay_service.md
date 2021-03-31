# nsxt_dhcp_relay_service

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
module "nsxt_dhcp_relay_service" {
  source = "./modules/nsxt/r/nsxt_dhcp_relay_service"

  # description - (optional) is a type of string
  description = null
  # dhcp_relay_profile_id - (required) is a type of string
  dhcp_relay_profile_id = null
  # display_name - (optional) is a type of string
  display_name = null

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

variable "dhcp_relay_profile_id" {
  description = "(required) - DHCP relay profile referenced by the dhcp relay service"
  type        = string
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
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
resource "nsxt_dhcp_relay_service" "this" {
  description           = var.description
  dhcp_relay_profile_id = var.dhcp_relay_profile_id
  display_name          = var.display_name

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
  value       = nsxt_dhcp_relay_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_dhcp_relay_service.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_dhcp_relay_service.this.revision
}

output "this" {
  value = nsxt_dhcp_relay_service.this
}
```

[top](#index)