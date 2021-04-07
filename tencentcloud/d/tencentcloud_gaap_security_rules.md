# tencentcloud_gaap_security_rules

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
module "tencentcloud_gaap_security_rules" {
  source = "./modules/tencentcloud/d/tencentcloud_gaap_security_rules"

  # action - (optional) is a type of string
  action = null
  # cidr_ip - (optional) is a type of string
  cidr_ip = null
  # name - (optional) is a type of string
  name = null
  # policy_id - (required) is a type of string
  policy_id = null
  # port - (optional) is a type of string
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # rule_id - (optional) is a type of string
  rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - Policy of the rule to be queried."
  type        = string
  default     = null
}

variable "cidr_ip" {
  description = "(optional) - A network address block of the request source to be queried."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the security policy rule to be queried."
  type        = string
  default     = null
}

variable "policy_id" {
  description = "(required) - ID of the security policy to be queried."
  type        = string
}

variable "port" {
  description = "(optional) - Port of the security policy rule to be queried."
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - Protocol of the security policy rule to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(optional) - ID of the security policy rules to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_gaap_security_rules" "this" {
  # action - (optional) is a type of string
  action = var.action
  # cidr_ip - (optional) is a type of string
  cidr_ip = var.cidr_ip
  # name - (optional) is a type of string
  name = var.name
  # policy_id - (required) is a type of string
  policy_id = var.policy_id
  # port - (optional) is a type of string
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
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
  value       = data.tencentcloud_gaap_security_rules.this.id
}

output "rules" {
  description = "returns a list of object"
  value       = data.tencentcloud_gaap_security_rules.this.rules
}

output "this" {
  value = tencentcloud_gaap_security_rules.this
}
```

[top](#index)