# constellix_tcp_check

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
module "constellix_tcp_check" {
  source = "./modules/constellix/d/constellix_tcp_check"

  # check_sites - (optional) is a type of list of number
  check_sites = []
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
  # port - (optional) is a type of number
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
  description = "(optional)"
  type        = list(number)
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

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
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

### Datasource

```terraform
data "constellix_tcp_check" "this" {
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
output "check_sites" {
  description = "returns a list of number"
  value       = data.constellix_tcp_check.this.check_sites
}

output "host" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.host
}

output "id" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.id
}

output "interval" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.interval
}

output "interval_policy" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.interval_policy
}

output "ip_version" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.ip_version
}

output "port" {
  description = "returns a number"
  value       = data.constellix_tcp_check.this.port
}

output "string_to_receive" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.string_to_receive
}

output "string_to_send" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.string_to_send
}

output "verification_policy" {
  description = "returns a string"
  value       = data.constellix_tcp_check.this.verification_policy
}

output "this" {
  value = constellix_tcp_check.this
}
```

[top](#index)