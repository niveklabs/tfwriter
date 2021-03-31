# dns_a_record_set

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
module "dns_a_record_set" {
  source = "./modules/dns/r/dns_a_record_set"

  # addresses - (required) is a type of set of string
  addresses = []
  # name - (optional) is a type of string
  name = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "addresses" {
  description = "(required)"
  type        = set(string)
}

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
```

[top](#index)

### Resource

```terraform
resource "dns_a_record_set" "this" {
  addresses = var.addresses
  name      = var.name
  ttl       = var.ttl
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dns_a_record_set.this.id
}

output "this" {
  value = dns_a_record_set.this
}
```

[top](#index)