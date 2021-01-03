# ovh_domain_zone_record

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_domain_zone_record" {
  source = "./modules/ovh/r/ovh_domain_zone_record"

  # fieldtype - (required) is a type of string
  fieldtype = null
  # subdomain - (optional) is a type of string
  subdomain = null
  # target - (required) is a type of string
  target = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "fieldtype" {
  description = "(required)"
  type        = string
}

variable "subdomain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_domain_zone_record" "this" {
  fieldtype = var.fieldtype
  subdomain = var.subdomain
  target    = var.target
  ttl       = var.ttl
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_domain_zone_record.this.id
}

output "this" {
  value = ovh_domain_zone_record.this
}
```

[top](#index)