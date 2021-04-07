# fortios_ips_custom

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_ips_custom" {
  source = "./modules/fortios/r/fortios_ips_custom"

  # action - (optional) is a type of string
  action = null
  # application - (optional) is a type of string
  application = null
  # comment - (optional) is a type of string
  comment = null
  # location - (optional) is a type of string
  location = null
  # log - (optional) is a type of string
  log = null
  # log_packet - (optional) is a type of string
  log_packet = null
  # os - (optional) is a type of string
  os = null
  # protocol - (optional) is a type of string
  protocol = null
  # rule_id - (optional) is a type of number
  rule_id = null
  # severity - (optional) is a type of string
  severity = null
  # sig_name - (optional) is a type of string
  sig_name = null
  # signature - (optional) is a type of string
  signature = null
  # status - (optional) is a type of string
  status = null
  # tag - (optional) is a type of string
  tag = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_packet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sig_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_custom" "this" {
  # action - (optional) is a type of string
  action = var.action
  # application - (optional) is a type of string
  application = var.application
  # comment - (optional) is a type of string
  comment = var.comment
  # location - (optional) is a type of string
  location = var.location
  # log - (optional) is a type of string
  log = var.log
  # log_packet - (optional) is a type of string
  log_packet = var.log_packet
  # os - (optional) is a type of string
  os = var.os
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # rule_id - (optional) is a type of number
  rule_id = var.rule_id
  # severity - (optional) is a type of string
  severity = var.severity
  # sig_name - (optional) is a type of string
  sig_name = var.sig_name
  # signature - (optional) is a type of string
  signature = var.signature
  # status - (optional) is a type of string
  status = var.status
  # tag - (optional) is a type of string
  tag = var.tag
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = fortios_ips_custom.this.action
}

output "application" {
  description = "returns a string"
  value       = fortios_ips_custom.this.application
}

output "comment" {
  description = "returns a string"
  value       = fortios_ips_custom.this.comment
}

output "id" {
  description = "returns a string"
  value       = fortios_ips_custom.this.id
}

output "location" {
  description = "returns a string"
  value       = fortios_ips_custom.this.location
}

output "log" {
  description = "returns a string"
  value       = fortios_ips_custom.this.log
}

output "log_packet" {
  description = "returns a string"
  value       = fortios_ips_custom.this.log_packet
}

output "os" {
  description = "returns a string"
  value       = fortios_ips_custom.this.os
}

output "protocol" {
  description = "returns a string"
  value       = fortios_ips_custom.this.protocol
}

output "rule_id" {
  description = "returns a number"
  value       = fortios_ips_custom.this.rule_id
}

output "severity" {
  description = "returns a string"
  value       = fortios_ips_custom.this.severity
}

output "sig_name" {
  description = "returns a string"
  value       = fortios_ips_custom.this.sig_name
}

output "signature" {
  description = "returns a string"
  value       = fortios_ips_custom.this.signature
}

output "status" {
  description = "returns a string"
  value       = fortios_ips_custom.this.status
}

output "tag" {
  description = "returns a string"
  value       = fortios_ips_custom.this.tag
}

output "this" {
  value = fortios_ips_custom.this
}
```

[top](#index)