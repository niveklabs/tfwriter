# alicloud_cr_ee_sync_rule

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
module "alicloud_cr_ee_sync_rule" {
  source = "./modules/alicloud/r/alicloud_cr_ee_sync_rule"

  # instance_id - (required) is a type of string
  instance_id = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # repo_name - (optional) is a type of string
  repo_name = null
  # tag_filter - (required) is a type of string
  tag_filter = null
  # target_instance_id - (required) is a type of string
  target_instance_id = null
  # target_namespace_name - (required) is a type of string
  target_namespace_name = null
  # target_region_id - (required) is a type of string
  target_region_id = null
  # target_repo_name - (optional) is a type of string
  target_repo_name = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "repo_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag_filter" {
  description = "(required)"
  type        = string
}

variable "target_instance_id" {
  description = "(required)"
  type        = string
}

variable "target_namespace_name" {
  description = "(required)"
  type        = string
}

variable "target_region_id" {
  description = "(required)"
  type        = string
}

variable "target_repo_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cr_ee_sync_rule" "this" {
  instance_id           = var.instance_id
  name                  = var.name
  namespace_name        = var.namespace_name
  repo_name             = var.repo_name
  tag_filter            = var.tag_filter
  target_instance_id    = var.target_instance_id
  target_namespace_name = var.target_namespace_name
  target_region_id      = var.target_region_id
  target_repo_name      = var.target_repo_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cr_ee_sync_rule.this.id
}

output "rule_id" {
  description = "returns a string"
  value       = alicloud_cr_ee_sync_rule.this.rule_id
}

output "sync_direction" {
  description = "returns a string"
  value       = alicloud_cr_ee_sync_rule.this.sync_direction
}

output "sync_scope" {
  description = "returns a string"
  value       = alicloud_cr_ee_sync_rule.this.sync_scope
}

output "this" {
  value = alicloud_cr_ee_sync_rule.this
}
```

[top](#index)