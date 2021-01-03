# oci_waas_custom_protection_rule

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_waas_custom_protection_rule" {
  source = "./modules/oci/d/oci_waas_custom_protection_rule"

  # custom_protection_rule_id - (required) is a type of string
  custom_protection_rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_protection_rule_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_custom_protection_rule" "this" {
  custom_protection_rule_id = var.custom_protection_rule_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_custom_protection_rule.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_custom_protection_rule.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.id
}

output "mod_security_rule_ids" {
  description = "returns a list of string"
  value       = data.oci_waas_custom_protection_rule.this.mod_security_rule_ids
}

output "state" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.state
}

output "template" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.template
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_waas_custom_protection_rule.this.time_created
}

output "this" {
  value = oci_waas_custom_protection_rule.this
}
```

[top](#index)