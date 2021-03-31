# ecl_dns_zone_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_dns_zone_v2" {
  source = "./modules/ecl/r/ecl_dns_zone_v2"

  # description - (optional) is a type of string
  description = null
  # email - (optional) is a type of string
  email = null
  # masters - (optional) is a type of set of string
  masters = []
  # name - (required) is a type of string
  name = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "masters" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_dns_zone_v2" "this" {
  description = var.description
  email       = var.email
  masters     = var.masters
  name        = var.name
  ttl         = var.ttl
  type        = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = ecl_dns_zone_v2.this.email
}

output "id" {
  description = "returns a string"
  value       = ecl_dns_zone_v2.this.id
}

output "masters" {
  description = "returns a set of string"
  value       = ecl_dns_zone_v2.this.masters
}

output "ttl" {
  description = "returns a number"
  value       = ecl_dns_zone_v2.this.ttl
}

output "type" {
  description = "returns a string"
  value       = ecl_dns_zone_v2.this.type
}

output "this" {
  value = ecl_dns_zone_v2.this
}
```

[top](#index)