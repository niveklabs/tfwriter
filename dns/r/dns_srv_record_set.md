# dns_srv_record_set

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
module "dns_srv_record_set" {
  source = "./modules/dns/r/dns_srv_record_set"

  # name - (required) is a type of string
  name = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone - (required) is a type of string
  zone = null

  srv = [{
    port     = null
    priority = null
    target   = null
    weight   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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

variable "srv" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      port     = number
      priority = number
      target   = string
      weight   = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "dns_srv_record_set" "this" {
  name = var.name
  ttl  = var.ttl
  zone = var.zone

  dynamic "srv" {
    for_each = var.srv
    content {
      port     = srv.value["port"]
      priority = srv.value["priority"]
      target   = srv.value["target"]
      weight   = srv.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dns_srv_record_set.this.id
}

output "this" {
  value = dns_srv_record_set.this
}
```

[top](#index)