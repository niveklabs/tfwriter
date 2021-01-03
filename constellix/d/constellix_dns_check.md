# constellix_dns_check

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/constellix/d/constellix_dns_check"

  # check_sites - (optional) is a type of list of number
  check_sites = []
  # expected_response - (optional) is a type of string
  expected_response = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # interval - (optional) is a type of string
  interval = null
  # interval_policy - (optional) is a type of string
  interval_policy = null
  # name - (required) is a type of string
  name = null
  # resolver - (optional) is a type of string
  resolver = null
  # verification_policy - (optional) is a type of string
  verification_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "check_sites" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "expected_response" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
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
  description = "(required)"
  type        = string
}

variable "resolver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "verification_policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "constellix_dns_check" "this" {
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
output "check_sites" {
  description = "returns a list of number"
  value       = data.constellix_dns_check.this.check_sites
}

output "expected_response" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.expected_response
}

output "fqdn" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.id
}

output "interval" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.interval
}

output "interval_policy" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.interval_policy
}

output "resolver" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.resolver
}

output "verification_policy" {
  description = "returns a string"
  value       = data.constellix_dns_check.this.verification_policy
}

output "this" {
  value = constellix_dns_check.this
}
```

[top](#index)