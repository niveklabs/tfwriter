# tencentcloud_clb_redirection

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
module "tencentcloud_clb_redirection" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_redirection"

  # clb_id - (required) is a type of string
  clb_id = null
  # delete_all_auto_rewrite - (optional) is a type of bool
  delete_all_auto_rewrite = null
  # is_auto_rewrite - (optional) is a type of bool
  is_auto_rewrite = null
  # source_listener_id - (optional) is a type of string
  source_listener_id = null
  # source_rule_id - (optional) is a type of string
  source_rule_id = null
  # target_listener_id - (required) is a type of string
  target_listener_id = null
  # target_rule_id - (required) is a type of string
  target_rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - ID of CLB instance."
  type        = string
}

variable "delete_all_auto_rewrite" {
  description = "(optional) - Indicates whether delete all auto redirection. Default is `false`. It will take effect only when this redirection is auto-rewrite and this auto-rewrite auto redirected more than one rules. All the auto-rewrite relations will be deleted when this parameter set true."
  type        = bool
  default     = null
}

variable "is_auto_rewrite" {
  description = "(optional) - Indicates whether automatic forwarding is enable, default is `false`. If enabled, the source listener and location should be empty, the target listener must be https protocol and port is 443."
  type        = bool
  default     = null
}

variable "source_listener_id" {
  description = "(optional) - ID of source listener."
  type        = string
  default     = null
}

variable "source_rule_id" {
  description = "(optional) - Rule ID of source listener."
  type        = string
  default     = null
}

variable "target_listener_id" {
  description = "(required) - ID of source listener."
  type        = string
}

variable "target_rule_id" {
  description = "(required) - Rule ID of target listener."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_redirection" "this" {
  # clb_id - (required) is a type of string
  clb_id = var.clb_id
  # delete_all_auto_rewrite - (optional) is a type of bool
  delete_all_auto_rewrite = var.delete_all_auto_rewrite
  # is_auto_rewrite - (optional) is a type of bool
  is_auto_rewrite = var.is_auto_rewrite
  # source_listener_id - (optional) is a type of string
  source_listener_id = var.source_listener_id
  # source_rule_id - (optional) is a type of string
  source_rule_id = var.source_rule_id
  # target_listener_id - (required) is a type of string
  target_listener_id = var.target_listener_id
  # target_rule_id - (required) is a type of string
  target_rule_id = var.target_rule_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_redirection.this.id
}

output "source_listener_id" {
  description = "returns a string"
  value       = tencentcloud_clb_redirection.this.source_listener_id
}

output "source_rule_id" {
  description = "returns a string"
  value       = tencentcloud_clb_redirection.this.source_rule_id
}

output "this" {
  value = tencentcloud_clb_redirection.this
}
```

[top](#index)