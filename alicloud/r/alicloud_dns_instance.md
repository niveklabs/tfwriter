# alicloud_dns_instance

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_dns_instance" {
  source = "./modules/alicloud/r/alicloud_dns_instance"

  # dns_security - (required) is a type of string
  dns_security = null
  # domain_numbers - (required) is a type of string
  domain_numbers = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # period - (optional) is a type of number
  period = null
  # renew_period - (optional) is a type of number
  renew_period = null
  # renewal_status - (optional) is a type of string
  renewal_status = null
  # version_code - (required) is a type of string
  version_code = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_security" {
  description = "(required)"
  type        = string
}

variable "domain_numbers" {
  description = "(required)"
  type        = string
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "renewal_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_code" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_dns_instance" "this" {
  # dns_security - (required) is a type of string
  dns_security = var.dns_security
  # domain_numbers - (required) is a type of string
  domain_numbers = var.domain_numbers
  # payment_type - (optional) is a type of string
  payment_type = var.payment_type
  # period - (optional) is a type of number
  period = var.period
  # renew_period - (optional) is a type of number
  renew_period = var.renew_period
  # renewal_status - (optional) is a type of string
  renewal_status = var.renewal_status
  # version_code - (required) is a type of string
  version_code = var.version_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_dns_instance.this.id
}

output "version_name" {
  description = "returns a string"
  value       = alicloud_dns_instance.this.version_name
}

output "this" {
  value = alicloud_dns_instance.this
}
```

[top](#index)