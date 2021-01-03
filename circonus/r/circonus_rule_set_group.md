# circonus_rule_set_group

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.11.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_rule_set_group" {
  source = "./modules/circonus/r/circonus_rule_set_group"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []

  condition = [{
    index               = null
    matching_severities = []
    rule_set            = null
  }]

  formula = [{
    expression     = null
    raise_severity = null
    wait           = null
  }]

  notify = [{
    sev1 = []
    sev2 = []
    sev3 = []
    sev4 = []
    sev5 = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "condition" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      index               = number
      matching_severities = list(string)
      rule_set            = string
    }
  ))
}

variable "formula" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      expression     = string
      raise_severity = number
      wait           = number
    }
  ))
}

variable "notify" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      sev1 = list(string)
      sev2 = list(string)
      sev3 = list(string)
      sev4 = list(string)
      sev5 = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "circonus_rule_set_group" "this" {
  name = var.name
  tags = var.tags

  dynamic "condition" {
    for_each = var.condition
    content {
      index               = condition.value["index"]
      matching_severities = condition.value["matching_severities"]
      rule_set            = condition.value["rule_set"]
    }
  }

  dynamic "formula" {
    for_each = var.formula
    content {
      expression     = formula.value["expression"]
      raise_severity = formula.value["raise_severity"]
      wait           = formula.value["wait"]
    }
  }

  dynamic "notify" {
    for_each = var.notify
    content {
      sev1 = notify.value["sev1"]
      sev2 = notify.value["sev2"]
      sev3 = notify.value["sev3"]
      sev4 = notify.value["sev4"]
      sev5 = notify.value["sev5"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = circonus_rule_set_group.this.id
}

output "this" {
  value = circonus_rule_set_group.this
}
```

[top](#index)