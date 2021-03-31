# oci_budget_alert_rule

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_budget_alert_rule" {
  source = "./modules/oci/r/oci_budget_alert_rule"

  # budget_id - (required) is a type of string
  budget_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # message - (optional) is a type of string
  message = null
  # recipients - (optional) is a type of string
  recipients = null
  # threshold - (required) is a type of number
  threshold = null
  # threshold_type - (required) is a type of string
  threshold_type = null
  # type - (required) is a type of string
  type = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "budget_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recipients" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold" {
  description = "(required)"
  type        = number
}

variable "threshold_type" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_budget_alert_rule" "this" {
  budget_id      = var.budget_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  message        = var.message
  recipients     = var.recipients
  threshold      = var.threshold
  threshold_type = var.threshold_type
  type           = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_budget_alert_rule.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_budget_alert_rule.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.id
}

output "message" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.message
}

output "state" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_budget_alert_rule.this.time_updated
}

output "version" {
  description = "returns a number"
  value       = oci_budget_alert_rule.this.version
}

output "this" {
  value = oci_budget_alert_rule.this
}
```

[top](#index)