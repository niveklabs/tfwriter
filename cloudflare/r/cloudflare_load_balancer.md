# cloudflare_load_balancer

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_load_balancer" {
  source = "./modules/cloudflare/r/cloudflare_load_balancer"

  # default_pool_ids - (required) is a type of list of string
  default_pool_ids = []
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # fallback_pool_id - (required) is a type of string
  fallback_pool_id = null
  # name - (required) is a type of string
  name = null
  # proxied - (optional) is a type of bool
  proxied = null
  # session_affinity - (optional) is a type of string
  session_affinity = null
  # session_affinity_attributes - (optional) is a type of map of string
  session_affinity_attributes = {}
  # session_affinity_ttl - (optional) is a type of number
  session_affinity_ttl = null
  # steering_policy - (optional) is a type of string
  steering_policy = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone_id - (required) is a type of string
  zone_id = null

  pop_pools = [{
    pool_ids = []
    pop      = null
  }]

  region_pools = [{
    pool_ids = []
    region   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_pool_ids" {
  description = "(required)"
  type        = list(string)
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fallback_pool_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "proxied" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "session_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_affinity_attributes" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "session_affinity_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "steering_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "pop_pools" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      pool_ids = list(string)
      pop      = string
    }
  ))
  default = []
}

variable "region_pools" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      pool_ids = list(string)
      region   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_load_balancer" "this" {
  # default_pool_ids - (required) is a type of list of string
  default_pool_ids = var.default_pool_ids
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # fallback_pool_id - (required) is a type of string
  fallback_pool_id = var.fallback_pool_id
  # name - (required) is a type of string
  name = var.name
  # proxied - (optional) is a type of bool
  proxied = var.proxied
  # session_affinity - (optional) is a type of string
  session_affinity = var.session_affinity
  # session_affinity_attributes - (optional) is a type of map of string
  session_affinity_attributes = var.session_affinity_attributes
  # session_affinity_ttl - (optional) is a type of number
  session_affinity_ttl = var.session_affinity_ttl
  # steering_policy - (optional) is a type of string
  steering_policy = var.steering_policy
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "pop_pools" {
    for_each = var.pop_pools
    content {
      # pool_ids - (required) is a type of list of string
      pool_ids = pop_pools.value["pool_ids"]
      # pop - (required) is a type of string
      pop = pop_pools.value["pop"]
    }
  }

  dynamic "region_pools" {
    for_each = var.region_pools
    content {
      # pool_ids - (required) is a type of list of string
      pool_ids = region_pools.value["pool_ids"]
      # region - (required) is a type of string
      region = region_pools.value["region"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_on" {
  description = "returns a string"
  value       = cloudflare_load_balancer.this.created_on
}

output "id" {
  description = "returns a string"
  value       = cloudflare_load_balancer.this.id
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_load_balancer.this.modified_on
}

output "steering_policy" {
  description = "returns a string"
  value       = cloudflare_load_balancer.this.steering_policy
}

output "ttl" {
  description = "returns a number"
  value       = cloudflare_load_balancer.this.ttl
}

output "this" {
  value = cloudflare_load_balancer.this
}
```

[top](#index)