# tencentcloud_gaap_security_rule

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_gaap_security_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_security_rule"

  # action - (required) is a type of string
  action = null
  # cidr_ip - (required) is a type of string
  cidr_ip = null
  # name - (optional) is a type of string
  name = null
  # policy_id - (required) is a type of string
  policy_id = null
  # port - (optional) is a type of string
  port = null
  # protocol - (optional) is a type of string
  protocol = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required) - Policy of the rule. Valid value: `ACCEPT` and `DROP`."
  type        = string
}

variable "cidr_ip" {
  description = "(required) - A network address block of the request source."
  type        = string
}

variable "name" {
  description = "(optional) - Name of the security policy rule. Maximum length is 30."
  type        = string
  default     = null
}

variable "policy_id" {
  description = "(required) - ID of the security policy."
  type        = string
}

variable "port" {
  description = "(optional) - Target port. Default value is `ALL`. Valid examples: `80`, `80,443` and `3306-20000`."
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - Protocol of the security policy rule. Default value is `ALL`. Valid value: `TCP`, `UDP` and `ALL`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_security_rule" "this" {
  # action - (required) is a type of string
  action = var.action
  # cidr_ip - (required) is a type of string
  cidr_ip = var.cidr_ip
  # name - (optional) is a type of string
  name = var.name
  # policy_id - (required) is a type of string
  policy_id = var.policy_id
  # port - (optional) is a type of string
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_security_rule.this.id
}

output "this" {
  value = tencentcloud_gaap_security_rule.this
}
```

[top](#index)