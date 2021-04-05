# alicloud_fc_trigger

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_fc_trigger" {
  source = "./modules/alicloud/r/alicloud_fc_trigger"

  # config - (optional) is a type of string
  config = null
  # config_mns - (optional) is a type of string
  config_mns = null
  # function - (required) is a type of string
  function = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # role - (optional) is a type of string
  role = null
  # service - (required) is a type of string
  service = null
  # source_arn - (optional) is a type of string
  source_arn = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_mns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "function" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "(required)"
  type        = string
}

variable "source_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_fc_trigger" "this" {
  config      = var.config
  config_mns  = var.config_mns
  function    = var.function
  name        = var.name
  name_prefix = var.name_prefix
  role        = var.role
  service     = var.service
  source_arn  = var.source_arn
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_fc_trigger.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = alicloud_fc_trigger.this.last_modified
}

output "name" {
  description = "returns a string"
  value       = alicloud_fc_trigger.this.name
}

output "trigger_id" {
  description = "returns a string"
  value       = alicloud_fc_trigger.this.trigger_id
}

output "this" {
  value = alicloud_fc_trigger.this
}
```

[top](#index)