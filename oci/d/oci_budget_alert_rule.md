# oci_budget_alert_rule

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_budget_alert_rule" {
  source = "./modules/oci/d/oci_budget_alert_rule"

  # alert_rule_id - (required) is a type of string
  alert_rule_id = null
  # budget_id - (required) is a type of string
  budget_id = null
}
```

[top](#index)

### Variables

```terraform
variable "alert_rule_id" {
  description = "(required)"
  type        = string
}

variable "budget_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_budget_alert_rule" "this" {
  alert_rule_id = var.alert_rule_id
  budget_id     = var.budget_id
}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_budget_alert_rule.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_budget_alert_rule.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.id
}

output "message" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.message
}

output "recipients" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.recipients
}

output "state" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.state
}

output "threshold" {
  description = "returns a number"
  value       = data.oci_budget_alert_rule.this.threshold
}

output "threshold_type" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.threshold_type
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.time_updated
}

output "type" {
  description = "returns a string"
  value       = data.oci_budget_alert_rule.this.type
}

output "version" {
  description = "returns a number"
  value       = data.oci_budget_alert_rule.this.version
}

output "this" {
  value = oci_budget_alert_rule.this
}
```

[top](#index)