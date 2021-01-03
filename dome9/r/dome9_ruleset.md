# dome9_ruleset

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_ruleset" {
  source = "./modules/dome9/r/dome9_ruleset"

  # cloud_vendor - (required) is a type of string
  cloud_vendor = null
  # description - (optional) is a type of string
  description = null
  # hide_in_compliance - (required) is a type of bool
  hide_in_compliance = null
  # is_template - (optional) is a type of bool
  is_template = null
  # language - (required) is a type of string
  language = null
  # name - (required) is a type of string
  name = null

  rules = [{
    compliance_tag = null
    control_title  = null
    description    = null
    domain         = null
    is_default     = null
    logic          = null
    logic_hash     = null
    name           = null
    priority       = null
    remediation    = null
    rule_id        = null
    severity       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_vendor" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hide_in_compliance" {
  description = "(required)"
  type        = bool
}

variable "is_template" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "language" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      compliance_tag = string
      control_title  = string
      description    = string
      domain         = string
      is_default     = bool
      logic          = string
      logic_hash     = string
      name           = string
      priority       = string
      remediation    = string
      rule_id        = string
      severity       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_ruleset" "this" {
  cloud_vendor       = var.cloud_vendor
  description        = var.description
  hide_in_compliance = var.hide_in_compliance
  is_template        = var.is_template
  language           = var.language
  name               = var.name

  dynamic "rules" {
    for_each = var.rules
    content {
      compliance_tag = rules.value["compliance_tag"]
      control_title  = rules.value["control_title"]
      description    = rules.value["description"]
      domain         = rules.value["domain"]
      is_default     = rules.value["is_default"]
      logic          = rules.value["logic"]
      name           = rules.value["name"]
      priority       = rules.value["priority"]
      remediation    = rules.value["remediation"]
      rule_id        = rules.value["rule_id"]
      severity       = rules.value["severity"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_time" {
  description = "returns a string"
  value       = dome9_ruleset.this.created_time
}

output "id" {
  description = "returns a string"
  value       = dome9_ruleset.this.id
}

output "min_feature_tier" {
  description = "returns a string"
  value       = dome9_ruleset.this.min_feature_tier
}

output "updated_time" {
  description = "returns a string"
  value       = dome9_ruleset.this.updated_time
}

output "this" {
  value = dome9_ruleset.this
}
```

[top](#index)