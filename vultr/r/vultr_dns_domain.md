# vultr_dns_domain

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
module "vultr_dns_domain" {
  source = "./modules/vultr/r/vultr_dns_domain"

  # dns_sec - (optional) is a type of string
  dns_sec = null
  # domain - (required) is a type of string
  domain = null
  # ip - (optional) is a type of string
  ip = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_sec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_dns_domain" "this" {
  # dns_sec - (optional) is a type of string
  dns_sec = var.dns_sec
  # domain - (required) is a type of string
  domain = var.domain
  # ip - (optional) is a type of string
  ip = var.ip
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_dns_domain.this.date_created
}

output "id" {
  description = "returns a string"
  value       = vultr_dns_domain.this.id
}

output "this" {
  value = vultr_dns_domain.this
}
```

[top](#index)