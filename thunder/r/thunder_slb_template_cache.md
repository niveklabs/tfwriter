# thunder_slb_template_cache

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_cache" {
  source = "./modules/thunder/r/thunder_slb_template_cache"

  # accept_reload_req - (optional) is a type of number
  accept_reload_req = null
  # age - (optional) is a type of number
  age = null
  # default_policy_nocache - (optional) is a type of number
  default_policy_nocache = null
  # disable_insert_age - (optional) is a type of number
  disable_insert_age = null
  # disable_insert_via - (optional) is a type of number
  disable_insert_via = null
  # logging - (optional) is a type of string
  logging = null
  # max_cache_size - (optional) is a type of number
  max_cache_size = null
  # max_content_size - (optional) is a type of number
  max_content_size = null
  # min_content_size - (optional) is a type of number
  min_content_size = null
  # name - (optional) is a type of string
  name = null
  # remove_cookies - (optional) is a type of number
  remove_cookies = null
  # replacement_policy - (optional) is a type of string
  replacement_policy = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # verify_host - (optional) is a type of number
  verify_host = null

  local_uri_policy = [{
    local_uri = null
  }]

  sampling_enable = [{
    counters1 = null
  }]

  uri_policy = [{
    cache_action = null
    cache_value  = null
    invalidate   = null
    uri          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accept_reload_req" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_policy_nocache" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_insert_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_insert_via" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "logging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_cache_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_content_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_content_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remove_cookies" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "replacement_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "verify_host" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_uri_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      local_uri = string
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}

variable "uri_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cache_action = string
      cache_value  = number
      invalidate   = string
      uri          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_cache" "this" {
  accept_reload_req      = var.accept_reload_req
  age                    = var.age
  default_policy_nocache = var.default_policy_nocache
  disable_insert_age     = var.disable_insert_age
  disable_insert_via     = var.disable_insert_via
  logging                = var.logging
  max_cache_size         = var.max_cache_size
  max_content_size       = var.max_content_size
  min_content_size       = var.min_content_size
  name                   = var.name
  remove_cookies         = var.remove_cookies
  replacement_policy     = var.replacement_policy
  user_tag               = var.user_tag
  uuid                   = var.uuid
  verify_host            = var.verify_host

  dynamic "local_uri_policy" {
    for_each = var.local_uri_policy
    content {
      local_uri = local_uri_policy.value["local_uri"]
    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

  dynamic "uri_policy" {
    for_each = var.uri_policy
    content {
      cache_action = uri_policy.value["cache_action"]
      cache_value  = uri_policy.value["cache_value"]
      invalidate   = uri_policy.value["invalidate"]
      uri          = uri_policy.value["uri"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_cache.this.id
}

output "this" {
  value = thunder_slb_template_cache.this
}
```

[top](#index)