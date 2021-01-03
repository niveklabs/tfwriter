# constellix_dns_check

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_dns_check" {
  source = "./modules/constellix/r/constellix_dns_check"

  # check_sites - (required) is a type of list of number
  check_sites = []
  # expected_response - (optional) is a type of string
  expected_response = null
  # fqdn - (required) is a type of string
  fqdn = null
  # interval - (optional) is a type of string
  interval = null
  # interval_policy - (optional) is a type of string
  interval_policy = null
  # name - (optional) is a type of string
  name = null
  # resolver - (required) is a type of string
  resolver = null
  # verification_policy - (optional) is a type of string
  verification_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "check_sites" {
  description = "(required)"
  type        = list(number)
}

variable "expected_response" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(required)"
  type        = string
}

variable "interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interval_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver" {
  description = "(required)"
  type        = string
}

variable "verification_policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "constellix_dns_check" "this" {
  check_sites         = var.check_sites
  expected_response   = var.expected_response
  fqdn                = var.fqdn
  interval            = var.interval
  interval_policy     = var.interval_policy
  name                = var.name
  resolver            = var.resolver
  verification_policy = var.verification_policy
}
```

[top](#index)

### Outputs

```terraform
output "expected_response" {
  description = "returns a string"
  value       = constellix_dns_check.this.expected_response
}

output "id" {
  description = "returns a string"
  value       = constellix_dns_check.this.id
}

output "interval" {
  description = "returns a string"
  value       = constellix_dns_check.this.interval
}

output "interval_policy" {
  description = "returns a string"
  value       = constellix_dns_check.this.interval_policy
}

output "name" {
  description = "returns a string"
  value       = constellix_dns_check.this.name
}

output "verification_policy" {
  description = "returns a string"
  value       = constellix_dns_check.this.verification_policy
}

output "this" {
  value = constellix_dns_check.this
}
```

[top](#index)