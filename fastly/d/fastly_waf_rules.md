# fastly_waf_rules

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_waf_rules" {
  source = "./modules/fastly/d/fastly_waf_rules"

  # exclude_modsec_rule_ids - (optional) is a type of list of number
  exclude_modsec_rule_ids = []
  # publishers - (optional) is a type of list of string
  publishers = []
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "exclude_modsec_rule_ids" {
  description = "(optional) - A list of modsecurity rules IDs to be excluded from the data set."
  type        = list(number)
  default     = null
}

variable "publishers" {
  description = "(optional) - A list of publishers to be used as filters for the data set."
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tags to be used as filters for the data set."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_waf_rules" "this" {
  # exclude_modsec_rule_ids - (optional) is a type of list of number
  exclude_modsec_rule_ids = var.exclude_modsec_rule_ids
  # publishers - (optional) is a type of list of string
  publishers = var.publishers
  # tags - (optional) is a type of list of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fastly_waf_rules.this.id
}

output "rules" {
  description = "returns a list of object"
  value       = data.fastly_waf_rules.this.rules
}

output "this" {
  value = fastly_waf_rules.this
}
```

[top](#index)