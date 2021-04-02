# oci_budget_budget

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_budget_budget" {
  source = "./modules/oci/d/oci_budget_budget"

  # budget_id - (required) is a type of string
  budget_id = null
}
```

[top](#index)

### Variables

```terraform
variable "budget_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_budget_budget" "this" {
  budget_id = var.budget_id
}
```

[top](#index)

### Outputs

```terraform
output "actual_spend" {
  description = "returns a number"
  value       = data.oci_budget_budget.this.actual_spend
}

output "alert_rule_count" {
  description = "returns a number"
  value       = data.oci_budget_budget.this.alert_rule_count
}

output "amount" {
  description = "returns a number"
  value       = data.oci_budget_budget.this.amount
}

output "budget_processing_period_start_offset" {
  description = "returns a number"
  value       = data.oci_budget_budget.this.budget_processing_period_start_offset
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_budget_budget.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.display_name
}

output "forecasted_spend" {
  description = "returns a number"
  value       = data.oci_budget_budget.this.forecasted_spend
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_budget_budget.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.id
}

output "reset_period" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.reset_period
}

output "state" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.state
}

output "target_compartment_id" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.target_compartment_id
}

output "target_type" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.target_type
}

output "targets" {
  description = "returns a list of string"
  value       = data.oci_budget_budget.this.targets
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.time_created
}

output "time_spend_computed" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.time_spend_computed
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_budget_budget.this.time_updated
}

output "version" {
  description = "returns a number"
  value       = data.oci_budget_budget.this.version
}

output "this" {
  value = oci_budget_budget.this
}
```

[top](#index)