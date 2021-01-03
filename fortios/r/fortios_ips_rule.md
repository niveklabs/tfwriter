# fortios_ips_rule

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_ips_rule" {
  source = "./modules/fortios/r/fortios_ips_rule"

  # action - (optional) is a type of string
  action = null
  # application - (optional) is a type of string
  application = null
  # date - (optional) is a type of number
  date = null
  # group - (optional) is a type of string
  group = null
  # location - (optional) is a type of string
  location = null
  # log - (optional) is a type of string
  log = null
  # log_packet - (optional) is a type of string
  log_packet = null
  # name - (optional) is a type of string
  name = null
  # os - (optional) is a type of string
  os = null
  # rev - (optional) is a type of number
  rev = null
  # rule_id - (optional) is a type of number
  rule_id = null
  # service - (optional) is a type of string
  service = null
  # severity - (optional) is a type of string
  severity = null
  # status - (optional) is a type of string
  status = null

  metadata = [{
    id      = null
    metaid  = null
    valueid = null
  }]
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

variable "date" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "group" {
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rev" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rule_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id      = number
      metaid  = number
      valueid = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_rule" "this" {
  action      = var.action
  application = var.application
  date        = var.date
  group       = var.group
  location    = var.location
  log         = var.log
  log_packet  = var.log_packet
  name        = var.name
  os          = var.os
  rev         = var.rev
  rule_id     = var.rule_id
  service     = var.service
  severity    = var.severity
  status      = var.status

  dynamic "metadata" {
    for_each = var.metadata
    content {
      id      = metadata.value["id"]
      metaid  = metadata.value["metaid"]
      valueid = metadata.value["valueid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = fortios_ips_rule.this.action
}

output "application" {
  description = "returns a string"
  value       = fortios_ips_rule.this.application
}

output "date" {
  description = "returns a number"
  value       = fortios_ips_rule.this.date
}

output "group" {
  description = "returns a string"
  value       = fortios_ips_rule.this.group
}

output "id" {
  description = "returns a string"
  value       = fortios_ips_rule.this.id
}

output "location" {
  description = "returns a string"
  value       = fortios_ips_rule.this.location
}

output "log" {
  description = "returns a string"
  value       = fortios_ips_rule.this.log
}

output "log_packet" {
  description = "returns a string"
  value       = fortios_ips_rule.this.log_packet
}

output "name" {
  description = "returns a string"
  value       = fortios_ips_rule.this.name
}

output "os" {
  description = "returns a string"
  value       = fortios_ips_rule.this.os
}

output "rev" {
  description = "returns a number"
  value       = fortios_ips_rule.this.rev
}

output "rule_id" {
  description = "returns a number"
  value       = fortios_ips_rule.this.rule_id
}

output "service" {
  description = "returns a string"
  value       = fortios_ips_rule.this.service
}

output "severity" {
  description = "returns a string"
  value       = fortios_ips_rule.this.severity
}

output "status" {
  description = "returns a string"
  value       = fortios_ips_rule.this.status
}

output "this" {
  value = fortios_ips_rule.this
}
```

[top](#index)