# constellix_http_check

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
module "constellix_http_check" {
  source = "./modules/constellix/r/constellix_http_check"

  # check_sites - (required) is a type of list of number
  check_sites = []
  # expected_status_code - (optional) is a type of number
  expected_status_code = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # host - (required) is a type of string
  host = null
  # interval - (optional) is a type of string
  interval = null
  # interval_policy - (optional) is a type of string
  interval_policy = null
  # ip_version - (required) is a type of string
  ip_version = null
  # name - (optional) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # port - (required) is a type of number
  port = null
  # protocol_type - (required) is a type of string
  protocol_type = null
  # search_string - (optional) is a type of string
  search_string = null
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

variable "expected_status_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
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

variable "ip_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol_type" {
  description = "(required)"
  type        = string
}

variable "search_string" {
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

### Resource

```terraform
resource "constellix_http_check" "this" {
  check_sites          = var.check_sites
  expected_status_code = var.expected_status_code
  fqdn                 = var.fqdn
  host                 = var.host
  interval             = var.interval
  interval_policy      = var.interval_policy
  ip_version           = var.ip_version
  name                 = var.name
  path                 = var.path
  port                 = var.port
  protocol_type        = var.protocol_type
  search_string        = var.search_string
  verification_policy  = var.verification_policy
}
```

[top](#index)

### Outputs

```terraform
output "expected_status_code" {
  description = "returns a number"
  value       = constellix_http_check.this.expected_status_code
}

output "fqdn" {
  description = "returns a string"
  value       = constellix_http_check.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = constellix_http_check.this.id
}

output "interval" {
  description = "returns a string"
  value       = constellix_http_check.this.interval
}

output "interval_policy" {
  description = "returns a string"
  value       = constellix_http_check.this.interval_policy
}

output "name" {
  description = "returns a string"
  value       = constellix_http_check.this.name
}

output "path" {
  description = "returns a string"
  value       = constellix_http_check.this.path
}

output "search_string" {
  description = "returns a string"
  value       = constellix_http_check.this.search_string
}

output "verification_policy" {
  description = "returns a string"
  value       = constellix_http_check.this.verification_policy
}

output "this" {
  value = constellix_http_check.this
}
```

[top](#index)