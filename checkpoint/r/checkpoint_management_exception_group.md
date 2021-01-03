# checkpoint_management_exception_group

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_exception_group" {
  source = "./modules/checkpoint/r/checkpoint_management_exception_group"

  # applied_profile - (optional) is a type of string
  applied_profile = null
  # apply_on - (optional) is a type of string
  apply_on = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []

  applied_threat_rules = [{
    layer    = null
    name     = null
    position = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "applied_profile" {
  description = "(optional) - The threat profile to apply this group to in the case of apply-on threat-rules-with-specific-profile."
  type        = string
  default     = null
}

variable "apply_on" {
  description = "(optional) - An exception group can be set to apply on all threat rules, all threat rules which have a specific profile, or those rules manually chosen by the user."
  type        = string
  default     = null
}

variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "applied_threat_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      layer    = string
      name     = string
      position = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_exception_group" "this" {
  applied_profile = var.applied_profile
  apply_on        = var.apply_on
  color           = var.color
  comments        = var.comments
  ignore_errors   = var.ignore_errors
  ignore_warnings = var.ignore_warnings
  name            = var.name
  tags            = var.tags

  dynamic "applied_threat_rules" {
    for_each = var.applied_threat_rules
    content {
      layer    = applied_threat_rules.value["layer"]
      name     = applied_threat_rules.value["name"]
      position = applied_threat_rules.value["position"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_exception_group.this.id
}

output "this" {
  value = checkpoint_management_exception_group.this
}
```

[top](#index)