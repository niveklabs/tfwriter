# cloudflare_load_balancer_pool

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
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_load_balancer_pool" {
  source = "./modules/cloudflare/r/cloudflare_load_balancer_pool"

  # check_regions - (optional) is a type of set of string
  check_regions = []
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # minimum_origins - (optional) is a type of number
  minimum_origins = null
  # monitor - (optional) is a type of string
  monitor = null
  # name - (required) is a type of string
  name = null
  # notification_email - (optional) is a type of string
  notification_email = null

  origins = [{
    address = null
    enabled = null
    name    = null
    weight  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "check_regions" {
  description = "(optional)"
  type        = set(string)
  default     = null
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

variable "minimum_origins" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origins" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      address = string
      enabled = bool
      name    = string
      weight  = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_load_balancer_pool" "this" {
  check_regions      = var.check_regions
  description        = var.description
  enabled            = var.enabled
  minimum_origins    = var.minimum_origins
  monitor            = var.monitor
  name               = var.name
  notification_email = var.notification_email

  dynamic "origins" {
    for_each = var.origins
    content {
      address = origins.value["address"]
      enabled = origins.value["enabled"]
      name    = origins.value["name"]
      weight  = origins.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "check_regions" {
  description = "returns a set of string"
  value       = cloudflare_load_balancer_pool.this.check_regions
}

output "created_on" {
  description = "returns a string"
  value       = cloudflare_load_balancer_pool.this.created_on
}

output "id" {
  description = "returns a string"
  value       = cloudflare_load_balancer_pool.this.id
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_load_balancer_pool.this.modified_on
}

output "this" {
  value = cloudflare_load_balancer_pool.this
}
```

[top](#index)