# oci_waas_protection_rule

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_waas_protection_rule" {
  source = "./modules/oci/r/oci_waas_protection_rule"

  # action - (optional) is a type of string
  action = null
  # key - (required) is a type of string
  key = null
  # waas_policy_id - (required) is a type of string
  waas_policy_id = null

  exclusions = [{
    exclusions = []
    target     = null
  }]

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
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "waas_policy_id" {
  description = "(required)"
  type        = string
}

variable "exclusions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      exclusions = list(string)
      target     = string
    }
  ))
  default = []
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
resource "oci_waas_protection_rule" "this" {
  action         = var.action
  key            = var.key
  waas_policy_id = var.waas_policy_id

  dynamic "exclusions" {
    for_each = var.exclusions
    content {
      exclusions = exclusions.value["exclusions"]
      target     = exclusions.value["target"]
    }
  }

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
output "action" {
  description = "returns a string"
  value       = oci_waas_protection_rule.this.action
}

output "description" {
  description = "returns a string"
  value       = oci_waas_protection_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = oci_waas_protection_rule.this.id
}

output "labels" {
  description = "returns a list of string"
  value       = oci_waas_protection_rule.this.labels
}

output "mod_security_rule_ids" {
  description = "returns a list of string"
  value       = oci_waas_protection_rule.this.mod_security_rule_ids
}

output "name" {
  description = "returns a string"
  value       = oci_waas_protection_rule.this.name
}

output "this" {
  value = oci_waas_protection_rule.this
}
```

[top](#index)