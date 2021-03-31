# cloudflare_zone_lockdown

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
module "cloudflare_zone_lockdown" {
  source = "./modules/cloudflare/r/cloudflare_zone_lockdown"

  # description - (optional) is a type of string
  description = null
  # paused - (optional) is a type of bool
  paused = null
  # priority - (optional) is a type of number
  priority = null
  # urls - (required) is a type of set of string
  urls = []
  # zone_id - (required) is a type of string
  zone_id = null

  configurations = [{
    target = null
    value  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "paused" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "urls" {
  description = "(required)"
  type        = set(string)
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "configurations" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      target = string
      value  = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_zone_lockdown" "this" {
  description = var.description
  paused      = var.paused
  priority    = var.priority
  urls        = var.urls
  zone_id     = var.zone_id

  dynamic "configurations" {
    for_each = var.configurations
    content {
      target = configurations.value["target"]
      value  = configurations.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_zone_lockdown.this.id
}

output "this" {
  value = cloudflare_zone_lockdown.this
}
```

[top](#index)