# nsxt_lb_cookie_persistence_profile

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
module "nsxt_lb_cookie_persistence_profile" {
  source = "./modules/nsxt/r/nsxt_lb_cookie_persistence_profile"

  # cookie_fallback - (optional) is a type of bool
  cookie_fallback = null
  # cookie_garble - (optional) is a type of bool
  cookie_garble = null
  # cookie_mode - (optional) is a type of string
  cookie_mode = null
  # cookie_name - (required) is a type of string
  cookie_name = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # persistence_shared - (optional) is a type of bool
  persistence_shared = null

  insert_mode_params = [{
    cookie_domain      = null
    cookie_expiry_type = null
    cookie_path        = null
    max_idle_time      = null
    max_life_time      = null
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
variable "cookie_fallback" {
  description = "(optional) - A boolean flag which reflects whether once the server points by this cookie is down, a new server is selected, or the requests will be rejected"
  type        = bool
  default     = null
}

variable "cookie_garble" {
  description = "(optional) - A boolean flag which reflects whether the cookie value (server IP and port) would be encrypted or in plain text"
  type        = bool
  default     = null
}

variable "cookie_mode" {
  description = "(optional) - The cookie persistence mode"
  type        = string
  default     = null
}

variable "cookie_name" {
  description = "(required) - The name of the cookie"
  type        = string
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

variable "persistence_shared" {
  description = "(optional) - A boolean flag which reflects whether the cookie persistence is private or shared"
  type        = bool
  default     = null
}

variable "insert_mode_params" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_domain      = string
      cookie_expiry_type = string
      cookie_path        = string
      max_idle_time      = number
      max_life_time      = number
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
resource "nsxt_lb_cookie_persistence_profile" "this" {
  cookie_fallback    = var.cookie_fallback
  cookie_garble      = var.cookie_garble
  cookie_mode        = var.cookie_mode
  cookie_name        = var.cookie_name
  description        = var.description
  display_name       = var.display_name
  persistence_shared = var.persistence_shared

  dynamic "insert_mode_params" {
    for_each = var.insert_mode_params
    content {
      cookie_domain      = insert_mode_params.value["cookie_domain"]
      cookie_expiry_type = insert_mode_params.value["cookie_expiry_type"]
      cookie_path        = insert_mode_params.value["cookie_path"]
      max_idle_time      = insert_mode_params.value["max_idle_time"]
      max_life_time      = insert_mode_params.value["max_life_time"]
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
  value       = nsxt_lb_cookie_persistence_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_cookie_persistence_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_cookie_persistence_profile.this.revision
}

output "this" {
  value = nsxt_lb_cookie_persistence_profile.this
}
```

[top](#index)