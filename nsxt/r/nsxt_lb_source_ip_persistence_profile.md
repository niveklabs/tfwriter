# nsxt_lb_source_ip_persistence_profile

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
module "nsxt_lb_source_ip_persistence_profile" {
  source = "./modules/nsxt/r/nsxt_lb_source_ip_persistence_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # ha_persistence_mirroring - (optional) is a type of bool
  ha_persistence_mirroring = null
  # persistence_shared - (optional) is a type of bool
  persistence_shared = null
  # purge_when_full - (optional) is a type of bool
  purge_when_full = null
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

variable "ha_persistence_mirroring" {
  description = "(optional) - A boolean flag which reflects whether persistence entries will be synchronized to the HA peer"
  type        = bool
  default     = null
}

variable "persistence_shared" {
  description = "(optional) - A boolean flag which reflects whether the cookie persistence is private or shared"
  type        = bool
  default     = null
}

variable "purge_when_full" {
  description = "(optional) - A boolean flag which reflects whether entries will be purged when the persistence table is full"
  type        = bool
  default     = null
}

variable "timeout" {
  description = "(optional) - Persistence expiration time in seconds, counted from the time all the connections are completed"
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
resource "nsxt_lb_source_ip_persistence_profile" "this" {
  description              = var.description
  display_name             = var.display_name
  ha_persistence_mirroring = var.ha_persistence_mirroring
  persistence_shared       = var.persistence_shared
  purge_when_full          = var.purge_when_full
  timeout                  = var.timeout

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
  value       = nsxt_lb_source_ip_persistence_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_source_ip_persistence_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_source_ip_persistence_profile.this.revision
}

output "this" {
  value = nsxt_lb_source_ip_persistence_profile.this
}
```

[top](#index)