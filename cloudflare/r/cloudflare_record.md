# cloudflare_record

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
module "cloudflare_record" {
  source = "./modules/cloudflare/r/cloudflare_record"

  # data - (optional) is a type of map of string
  data = {}
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # proxied - (optional) is a type of bool
  proxied = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # value - (optional) is a type of string
  value = null
  # zone_id - (required) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxied" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_record" "this" {
  # data - (optional) is a type of map of string
  data = var.data
  # name - (required) is a type of string
  name = var.name
  # priority - (optional) is a type of number
  priority = var.priority
  # proxied - (optional) is a type of bool
  proxied = var.proxied
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # value - (optional) is a type of string
  value = var.value
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_on" {
  description = "returns a string"
  value       = cloudflare_record.this.created_on
}

output "hostname" {
  description = "returns a string"
  value       = cloudflare_record.this.hostname
}

output "id" {
  description = "returns a string"
  value       = cloudflare_record.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = cloudflare_record.this.metadata
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_record.this.modified_on
}

output "proxiable" {
  description = "returns a bool"
  value       = cloudflare_record.this.proxiable
}

output "ttl" {
  description = "returns a number"
  value       = cloudflare_record.this.ttl
}

output "value" {
  description = "returns a string"
  value       = cloudflare_record.this.value
}

output "this" {
  value = cloudflare_record.this
}
```

[top](#index)