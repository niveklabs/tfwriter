# alicloud_resource_manager_policy_attachments

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
module "alicloud_resource_manager_policy_attachments" {
  source = "./modules/alicloud/d/alicloud_resource_manager_policy_attachments"

  # language - (optional) is a type of string
  language = null
  # output_file - (optional) is a type of string
  output_file = null
  # policy_name - (optional) is a type of string
  policy_name = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # principal_name - (optional) is a type of string
  principal_name = null
  # principal_type - (optional) is a type of string
  principal_type = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_policy_attachments" "this" {
  # language - (optional) is a type of string
  language = var.language
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # policy_name - (optional) is a type of string
  policy_name = var.policy_name
  # policy_type - (optional) is a type of string
  policy_type = var.policy_type
  # principal_name - (optional) is a type of string
  principal_name = var.principal_name
  # principal_type - (optional) is a type of string
  principal_type = var.principal_type
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
}
```

[top](#index)

### Outputs

```terraform
output "attachments" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_policy_attachments.this.attachments
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_policy_attachments.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_policy_attachments.this.ids
}

output "this" {
  value = alicloud_resource_manager_policy_attachments.this
}
```

[top](#index)