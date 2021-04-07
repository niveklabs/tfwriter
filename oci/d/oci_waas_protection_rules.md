# oci_waas_protection_rules

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
module "oci_waas_protection_rules" {
  source = "./modules/oci/d/oci_waas_protection_rules"

  # action - (optional) is a type of list of string
  action = []
  # mod_security_rule_id - (optional) is a type of list of string
  mod_security_rule_id = []
  # waas_policy_id - (required) is a type of string
  waas_policy_id = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "mod_security_rule_id" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "waas_policy_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_protection_rules" "this" {
  action               = var.action
  mod_security_rule_id = var.mod_security_rule_id
  waas_policy_id       = var.waas_policy_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_waas_protection_rules.this.id
}

output "protection_rules" {
  description = "returns a list of object"
  value       = data.oci_waas_protection_rules.this.protection_rules
}

output "this" {
  value = oci_waas_protection_rules.this
}
```

[top](#index)