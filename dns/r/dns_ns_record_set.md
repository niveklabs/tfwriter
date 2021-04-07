# dns_ns_record_set

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
module "dns_ns_record_set" {
  source = "./modules/dns/r/dns_ns_record_set"

  # name - (required) is a type of string
  name = null
  # nameservers - (required) is a type of set of string
  nameservers = []
  # ttl - (optional) is a type of number
  ttl = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "nameservers" {
  description = "(required)"
  type        = set(string)
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
resource "dns_ns_record_set" "this" {
  # name - (required) is a type of string
  name = var.name
  # nameservers - (required) is a type of set of string
  nameservers = var.nameservers
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # zone - (required) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dns_ns_record_set.this.id
}

output "this" {
  value = dns_ns_record_set.this
}
```

[top](#index)