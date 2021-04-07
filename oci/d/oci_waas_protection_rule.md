# oci_waas_protection_rule

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
module "oci_waas_protection_rule" {
  source = "./modules/oci/d/oci_waas_protection_rule"

  # protection_rule_key - (required) is a type of string
  protection_rule_key = null
  # waas_policy_id - (required) is a type of string
  waas_policy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "protection_rule_key" {
  description = "(required)"
  type        = string
}

variable "waas_policy_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_protection_rule" "this" {
  # protection_rule_key - (required) is a type of string
  protection_rule_key = var.protection_rule_key
  # waas_policy_id - (required) is a type of string
  waas_policy_id = var.waas_policy_id
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.oci_waas_protection_rule.this.action
}

output "description" {
  description = "returns a string"
  value       = data.oci_waas_protection_rule.this.description
}

output "exclusions" {
  description = "returns a list of object"
  value       = data.oci_waas_protection_rule.this.exclusions
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_protection_rule.this.id
}

output "key" {
  description = "returns a string"
  value       = data.oci_waas_protection_rule.this.key
}

output "labels" {
  description = "returns a list of string"
  value       = data.oci_waas_protection_rule.this.labels
}

output "mod_security_rule_ids" {
  description = "returns a list of string"
  value       = data.oci_waas_protection_rule.this.mod_security_rule_ids
}

output "name" {
  description = "returns a string"
  value       = data.oci_waas_protection_rule.this.name
}

output "this" {
  value = oci_waas_protection_rule.this
}
```

[top](#index)