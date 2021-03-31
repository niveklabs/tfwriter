# dme_custom_soa_record

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_custom_soa_record" {
  source = "./modules/dme/r/dme_custom_soa_record"

  # comp - (required) is a type of string
  comp = null
  # email - (required) is a type of string
  email = null
  # expire - (required) is a type of number
  expire = null
  # name - (required) is a type of string
  name = null
  # negative_cache - (required) is a type of number
  negative_cache = null
  # refresh - (required) is a type of number
  refresh = null
  # retry - (required) is a type of number
  retry = null
  # serial - (required) is a type of number
  serial = null
  # ttl - (required) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "comp" {
  description = "(required)"
  type        = string
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "expire" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "negative_cache" {
  description = "(required)"
  type        = number
}

variable "refresh" {
  description = "(required)"
  type        = number
}

variable "retry" {
  description = "(required)"
  type        = number
}

variable "serial" {
  description = "(required)"
  type        = number
}

variable "ttl" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "dme_custom_soa_record" "this" {
  comp           = var.comp
  email          = var.email
  expire         = var.expire
  name           = var.name
  negative_cache = var.negative_cache
  refresh        = var.refresh
  retry          = var.retry
  serial         = var.serial
  ttl            = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dme_custom_soa_record.this.id
}

output "this" {
  value = dme_custom_soa_record.this
}
```

[top](#index)