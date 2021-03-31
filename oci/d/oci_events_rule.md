# oci_events_rule

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_events_rule" {
  source = "./modules/oci/d/oci_events_rule"

  # rule_id - (required) is a type of string
  rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "rule_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_events_rule" "this" {
  rule_id = var.rule_id
}
```

[top](#index)

### Outputs

```terraform
output "actions" {
  description = "returns a list of object"
  value       = data.oci_events_rule.this.actions
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_events_rule.this.compartment_id
}

output "condition" {
  description = "returns a string"
  value       = data.oci_events_rule.this.condition
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_events_rule.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_events_rule.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_events_rule.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_events_rule.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_events_rule.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_events_rule.this.is_enabled
}

output "lifecycle_message" {
  description = "returns a string"
  value       = data.oci_events_rule.this.lifecycle_message
}

output "state" {
  description = "returns a string"
  value       = data.oci_events_rule.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_events_rule.this.time_created
}

output "this" {
  value = oci_events_rule.this
}
```

[top](#index)