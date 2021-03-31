# dns_mx_record_set

[back](../dns.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dns = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dns_mx_record_set" {
  source = "./modules/dns/r/dns_mx_record_set"

  # name - (optional) is a type of string
  name = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone - (required) is a type of string
  zone = null

  mx = [{
    exchange   = null
    preference = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "mx" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      exchange   = string
      preference = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "dns_mx_record_set" "this" {
  name = var.name
  ttl  = var.ttl
  zone = var.zone

  dynamic "mx" {
    for_each = var.mx
    content {
      exchange   = mx.value["exchange"]
      preference = mx.value["preference"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dns_mx_record_set.this.id
}

output "this" {
  value = dns_mx_record_set.this
}
```

[top](#index)