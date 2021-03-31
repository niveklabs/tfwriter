# datadog_security_monitoring_rules

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "datadog_security_monitoring_rules" {
  source = "./modules/datadog/d/datadog_security_monitoring_rules"

  # default_only_filter - (optional) is a type of bool
  default_only_filter = null
  # name_filter - (optional) is a type of string
  name_filter = null
  # tags_filter - (optional) is a type of list of string
  tags_filter = []
  # user_only_filter - (optional) is a type of bool
  user_only_filter = null
}
```

[top](#index)

### Variables

```terraform
variable "default_only_filter" {
  description = "(optional) - Limit the search to default rules"
  type        = bool
  default     = null
}

variable "name_filter" {
  description = "(optional) - A rule name to limit the search"
  type        = string
  default     = null
}

variable "tags_filter" {
  description = "(optional) - A list of tags to limit the search"
  type        = list(string)
  default     = null
}

variable "user_only_filter" {
  description = "(optional) - Limit the search to user rules"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "datadog_security_monitoring_rules" "this" {
  default_only_filter = var.default_only_filter
  name_filter         = var.name_filter
  tags_filter         = var.tags_filter
  user_only_filter    = var.user_only_filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.datadog_security_monitoring_rules.this.id
}

output "rule_ids" {
  description = "returns a list of string"
  value       = data.datadog_security_monitoring_rules.this.rule_ids
}

output "rules" {
  description = "returns a list of object"
  value       = data.datadog_security_monitoring_rules.this.rules
}

output "this" {
  value = datadog_security_monitoring_rules.this
}
```

[top](#index)