# dns_cname_record

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
    dns = ">= 3.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dns_cname_record" {
  source = "./modules/dns/r/dns_cname_record"

  # cname - (required) is a type of string
  cname = null
  # name - (required) is a type of string
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
variable "cname" {
  description = "(required)"
  type        = string
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

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dns_cname_record" "this" {
  cname = var.cname
  name  = var.name
  ttl   = var.ttl
  zone  = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dns_cname_record.this.id
}

output "this" {
  value = dns_cname_record.this
}
```

[top](#index)