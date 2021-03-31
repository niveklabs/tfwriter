# constellix_tcp_check

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
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_tcp_check" {
  source = "./modules/constellix/r/constellix_tcp_check"

  # check_sites - (required) is a type of list of number
  check_sites = []
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
  # port - (required) is a type of number
  port = null
  # string_to_receive - (optional) is a type of string
  string_to_receive = null
  # string_to_send - (optional) is a type of string
  string_to_send = null
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

variable "port" {
  description = "(required)"
  type        = number
}

variable "string_to_receive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "string_to_send" {
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
resource "constellix_tcp_check" "this" {
  check_sites         = var.check_sites
  host                = var.host
  interval            = var.interval
  interval_policy     = var.interval_policy
  ip_version          = var.ip_version
  name                = var.name
  port                = var.port
  string_to_receive   = var.string_to_receive
  string_to_send      = var.string_to_send
  verification_policy = var.verification_policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = constellix_tcp_check.this.id
}

output "interval" {
  description = "returns a string"
  value       = constellix_tcp_check.this.interval
}

output "interval_policy" {
  description = "returns a string"
  value       = constellix_tcp_check.this.interval_policy
}

output "name" {
  description = "returns a string"
  value       = constellix_tcp_check.this.name
}

output "string_to_receive" {
  description = "returns a string"
  value       = constellix_tcp_check.this.string_to_receive
}

output "string_to_send" {
  description = "returns a string"
  value       = constellix_tcp_check.this.string_to_send
}

output "verification_policy" {
  description = "returns a string"
  value       = constellix_tcp_check.this.verification_policy
}

output "this" {
  value = constellix_tcp_check.this
}
```

[top](#index)