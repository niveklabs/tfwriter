# vultr_dns_record

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_dns_record" {
  source = "./modules/vultr/r/vultr_dns_record"

  # data - (required) is a type of string
  data = null
  # domain - (required) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "data" {
  description = "(required)"
  type        = string
}

variable "domain" {
  description = "(required)"
  type        = string
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

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_dns_record" "this" {
  # data - (required) is a type of string
  data = var.data
  # domain - (required) is a type of string
  domain = var.domain
  # name - (required) is a type of string
  name = var.name
  # priority - (optional) is a type of number
  priority = var.priority
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vultr_dns_record.this.id
}

output "this" {
  value = vultr_dns_record.this
}
```

[top](#index)