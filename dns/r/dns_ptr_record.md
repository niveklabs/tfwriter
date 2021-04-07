# dns_ptr_record

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
module "dns_ptr_record" {
  source = "./modules/dns/r/dns_ptr_record"

  # name - (optional) is a type of string
  name = null
  # ptr - (required) is a type of string
  ptr = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "ptr" {
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
resource "dns_ptr_record" "this" {
  # name - (optional) is a type of string
  name = var.name
  # ptr - (required) is a type of string
  ptr = var.ptr
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
  value       = dns_ptr_record.this.id
}

output "this" {
  value = dns_ptr_record.this
}
```

[top](#index)