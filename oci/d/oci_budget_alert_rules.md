# oci_budget_alert_rules

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
module "oci_budget_alert_rules" {
  source = "./modules/oci/d/oci_budget_alert_rules"

  # budget_id - (required) is a type of string
  budget_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # state - (optional) is a type of string
  state = null

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
variable "budget_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
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
data "oci_budget_alert_rules" "this" {
  budget_id    = var.budget_id
  display_name = var.display_name
  state        = var.state

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
output "alert_rules" {
  description = "returns a list of object"
  value       = data.oci_budget_alert_rules.this.alert_rules
}

output "id" {
  description = "returns a string"
  value       = data.oci_budget_alert_rules.this.id
}

output "this" {
  value = oci_budget_alert_rules.this
}
```

[top](#index)