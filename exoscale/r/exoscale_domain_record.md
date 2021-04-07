# exoscale_domain_record

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_domain_record" {
  source = "./modules/exoscale/r/exoscale_domain_record"

  # content - (required) is a type of string
  content = null
  # domain - (required) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # prio - (optional) is a type of number
  prio = null
  # record_type - (required) is a type of string
  record_type = null
  # ttl - (optional) is a type of number
  ttl = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "content" {
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

variable "prio" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "record_type" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_domain_record" "this" {
  # content - (required) is a type of string
  content = var.content
  # domain - (required) is a type of string
  domain = var.domain
  # name - (required) is a type of string
  name = var.name
  # prio - (optional) is a type of number
  prio = var.prio
  # record_type - (required) is a type of string
  record_type = var.record_type
  # ttl - (optional) is a type of number
  ttl = var.ttl

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "hostname" {
  description = "returns a string"
  value       = exoscale_domain_record.this.hostname
}

output "id" {
  description = "returns a string"
  value       = exoscale_domain_record.this.id
}

output "prio" {
  description = "returns a number"
  value       = exoscale_domain_record.this.prio
}

output "ttl" {
  description = "returns a number"
  value       = exoscale_domain_record.this.ttl
}

output "this" {
  value = exoscale_domain_record.this
}
```

[top](#index)