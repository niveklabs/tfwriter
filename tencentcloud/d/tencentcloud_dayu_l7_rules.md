# tencentcloud_dayu_l7_rules

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_dayu_l7_rules" {
  source = "./modules/tencentcloud/d/tencentcloud_dayu_l7_rules"

  # domain - (optional) is a type of string
  domain = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # rule_id - (optional) is a type of string
  rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - Domain of the layer 7 rule to be queried."
  type        = string
  default     = null
}

variable "resource_id" {
  description = "(required) - Id of the resource that the layer 7 rule works for."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the layer 7 rule works for, valid value is `bgpip`."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(optional) - Id of the layer 7 rule to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_dayu_l7_rules" "this" {
  # domain - (optional) is a type of string
  domain = var.domain
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # rule_id - (optional) is a type of string
  rule_id = var.rule_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_dayu_l7_rules.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_dayu_l7_rules.this.list
}

output "this" {
  value = tencentcloud_dayu_l7_rules.this
}
```

[top](#index)