# nsxt_mac_management_switching_profile

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
module "nsxt_mac_management_switching_profile" {
  source = "./modules/nsxt/r/nsxt_mac_management_switching_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # mac_change_allowed - (optional) is a type of bool
  mac_change_allowed = null

  mac_learning = [{
    enabled                  = null
    limit                    = null
    limit_policy             = null
    unicast_flooding_allowed = null
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

variable "mac_change_allowed" {
  description = "(optional) - Allowing source MAC address change"
  type        = bool
  default     = null
}

variable "mac_learning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled                  = bool
      limit                    = number
      limit_policy             = string
      unicast_flooding_allowed = bool
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
resource "nsxt_mac_management_switching_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # mac_change_allowed - (optional) is a type of bool
  mac_change_allowed = var.mac_change_allowed

  dynamic "mac_learning" {
    for_each = var.mac_learning
    content {
      # enabled - (optional) is a type of bool
      enabled = mac_learning.value["enabled"]
      # limit - (optional) is a type of number
      limit = mac_learning.value["limit"]
      # limit_policy - (optional) is a type of string
      limit_policy = mac_learning.value["limit_policy"]
      # unicast_flooding_allowed - (optional) is a type of bool
      unicast_flooding_allowed = mac_learning.value["unicast_flooding_allowed"]
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
  value       = nsxt_mac_management_switching_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_mac_management_switching_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_mac_management_switching_profile.this.revision
}

output "this" {
  value = nsxt_mac_management_switching_profile.this
}
```

[top](#index)