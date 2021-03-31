# datadog_security_monitoring_default_rule

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_security_monitoring_default_rule" {
  source = "./modules/datadog/r/datadog_security_monitoring_default_rule"

  # enabled - (optional) is a type of bool
  enabled = null

  case = [{
    notifications = []
    status        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Enable the rule."
  type        = bool
  default     = null
}

variable "case" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      notifications = list(string)
      status        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_security_monitoring_default_rule" "this" {
  enabled = var.enabled

  dynamic "case" {
    for_each = var.case
    content {
      notifications = case.value["notifications"]
      status        = case.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_security_monitoring_default_rule.this.id
}

output "this" {
  value = datadog_security_monitoring_default_rule.this
}
```

[top](#index)