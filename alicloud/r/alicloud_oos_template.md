# alicloud_oos_template

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
module "alicloud_oos_template" {
  source = "./modules/alicloud/r/alicloud_oos_template"

  # auto_delete_executions - (optional) is a type of bool
  auto_delete_executions = null
  # content - (required) is a type of string
  content = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_name - (required) is a type of string
  template_name = null
  # version_name - (optional) is a type of string
  version_name = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_delete_executions" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "content" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "version_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_oos_template" "this" {
  # auto_delete_executions - (optional) is a type of bool
  auto_delete_executions = var.auto_delete_executions
  # content - (required) is a type of string
  content = var.content
  # tags - (optional) is a type of map of string
  tags = var.tags
  # template_name - (required) is a type of string
  template_name = var.template_name
  # version_name - (optional) is a type of string
  version_name = var.version_name
}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = alicloud_oos_template.this.created_by
}

output "created_date" {
  description = "returns a string"
  value       = alicloud_oos_template.this.created_date
}

output "description" {
  description = "returns a string"
  value       = alicloud_oos_template.this.description
}

output "has_trigger" {
  description = "returns a bool"
  value       = alicloud_oos_template.this.has_trigger
}

output "id" {
  description = "returns a string"
  value       = alicloud_oos_template.this.id
}

output "share_type" {
  description = "returns a string"
  value       = alicloud_oos_template.this.share_type
}

output "template_format" {
  description = "returns a string"
  value       = alicloud_oos_template.this.template_format
}

output "template_id" {
  description = "returns a string"
  value       = alicloud_oos_template.this.template_id
}

output "template_type" {
  description = "returns a string"
  value       = alicloud_oos_template.this.template_type
}

output "template_version" {
  description = "returns a string"
  value       = alicloud_oos_template.this.template_version
}

output "updated_by" {
  description = "returns a string"
  value       = alicloud_oos_template.this.updated_by
}

output "updated_date" {
  description = "returns a string"
  value       = alicloud_oos_template.this.updated_date
}

output "this" {
  value = alicloud_oos_template.this
}
```

[top](#index)