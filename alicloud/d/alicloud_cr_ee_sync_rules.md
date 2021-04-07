# alicloud_cr_ee_sync_rules

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_cr_ee_sync_rules" {
  source = "./modules/alicloud/d/alicloud_cr_ee_sync_rules"

  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # namespace_name - (optional) is a type of string
  namespace_name = null
  # output_file - (optional) is a type of string
  output_file = null
  # repo_name - (optional) is a type of string
  repo_name = null
  # target_instance_id - (optional) is a type of string
  target_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repo_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cr_ee_sync_rules" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # namespace_name - (optional) is a type of string
  namespace_name = var.namespace_name
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # repo_name - (optional) is a type of string
  repo_name = var.repo_name
  # target_instance_id - (optional) is a type of string
  target_instance_id = var.target_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cr_ee_sync_rules.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cr_ee_sync_rules.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cr_ee_sync_rules.this.names
}

output "rules" {
  description = "returns a list of object"
  value       = data.alicloud_cr_ee_sync_rules.this.rules
}

output "this" {
  value = alicloud_cr_ee_sync_rules.this
}
```

[top](#index)