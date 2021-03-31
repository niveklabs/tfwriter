# constellix_http_check

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
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_http_check" {
  source = "./modules/constellix/d/constellix_http_check"

  # check_sites - (optional) is a type of list of number
  check_sites = []
  # expected_status_code - (optional) is a type of number
  expected_status_code = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # host - (optional) is a type of string
  host = null
  # interval - (optional) is a type of string
  interval = null
  # interval_policy - (optional) is a type of string
  interval_policy = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # port - (optional) is a type of number
  port = null
  # protocol_type - (optional) is a type of string
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
  description = "(optional)"
  type        = list(number)
  default     = null
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

variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol_type" {
  description = "(optional)"
  type        = string
  default     = null
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

### Datasource

```terraform
data "constellix_http_check" "this" {
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
output "check_sites" {
  description = "returns a list of number"
  value       = data.constellix_http_check.this.check_sites
}

output "expected_status_code" {
  description = "returns a number"
  value       = data.constellix_http_check.this.expected_status_code
}

output "fqdn" {
  description = "returns a string"
  value       = data.constellix_http_check.this.fqdn
}

output "host" {
  description = "returns a string"
  value       = data.constellix_http_check.this.host
}

output "id" {
  description = "returns a string"
  value       = data.constellix_http_check.this.id
}

output "interval" {
  description = "returns a string"
  value       = data.constellix_http_check.this.interval
}

output "interval_policy" {
  description = "returns a string"
  value       = data.constellix_http_check.this.interval_policy
}

output "ip_version" {
  description = "returns a string"
  value       = data.constellix_http_check.this.ip_version
}

output "path" {
  description = "returns a string"
  value       = data.constellix_http_check.this.path
}

output "port" {
  description = "returns a number"
  value       = data.constellix_http_check.this.port
}

output "protocol_type" {
  description = "returns a string"
  value       = data.constellix_http_check.this.protocol_type
}

output "search_string" {
  description = "returns a string"
  value       = data.constellix_http_check.this.search_string
}

output "verification_policy" {
  description = "returns a string"
  value       = data.constellix_http_check.this.verification_policy
}

output "this" {
  value = constellix_http_check.this
}
```

[top](#index)