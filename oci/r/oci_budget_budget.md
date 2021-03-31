# oci_budget_budget

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
module "oci_budget_budget" {
  source = "./modules/oci/r/oci_budget_budget"

  # amount - (required) is a type of number
  amount = null
  # budget_processing_period_start_offset - (optional) is a type of number
  budget_processing_period_start_offset = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # reset_period - (required) is a type of string
  reset_period = null
  # target_compartment_id - (optional) is a type of string
  target_compartment_id = null
  # target_type - (optional) is a type of string
  target_type = null
  # targets - (optional) is a type of list of string
  targets = []

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
variable "amount" {
  description = "(required)"
  type        = number
}

variable "budget_processing_period_start_offset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compartment_id" {
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

variable "reset_period" {
  description = "(required)"
  type        = string
}

variable "target_compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "targets" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
resource "oci_budget_budget" "this" {
  amount                                = var.amount
  budget_processing_period_start_offset = var.budget_processing_period_start_offset
  compartment_id                        = var.compartment_id
  defined_tags                          = var.defined_tags
  description                           = var.description
  display_name                          = var.display_name
  freeform_tags                         = var.freeform_tags
  reset_period                          = var.reset_period
  target_compartment_id                 = var.target_compartment_id
  target_type                           = var.target_type
  targets                               = var.targets

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
output "actual_spend" {
  description = "returns a number"
  value       = oci_budget_budget.this.actual_spend
}

output "alert_rule_count" {
  description = "returns a number"
  value       = oci_budget_budget.this.alert_rule_count
}

output "budget_processing_period_start_offset" {
  description = "returns a number"
  value       = oci_budget_budget.this.budget_processing_period_start_offset
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_budget_budget.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_budget_budget.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_budget_budget.this.display_name
}

output "forecasted_spend" {
  description = "returns a number"
  value       = oci_budget_budget.this.forecasted_spend
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_budget_budget.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_budget_budget.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_budget_budget.this.state
}

output "target_compartment_id" {
  description = "returns a string"
  value       = oci_budget_budget.this.target_compartment_id
}

output "target_type" {
  description = "returns a string"
  value       = oci_budget_budget.this.target_type
}

output "targets" {
  description = "returns a list of string"
  value       = oci_budget_budget.this.targets
}

output "time_created" {
  description = "returns a string"
  value       = oci_budget_budget.this.time_created
}

output "time_spend_computed" {
  description = "returns a string"
  value       = oci_budget_budget.this.time_spend_computed
}

output "time_updated" {
  description = "returns a string"
  value       = oci_budget_budget.this.time_updated
}

output "version" {
  description = "returns a number"
  value       = oci_budget_budget.this.version
}

output "this" {
  value = oci_budget_budget.this
}
```

[top](#index)