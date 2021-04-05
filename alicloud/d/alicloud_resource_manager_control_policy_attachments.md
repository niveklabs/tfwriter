# alicloud_resource_manager_control_policy_attachments

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
module "alicloud_resource_manager_control_policy_attachments" {
  source = "./modules/alicloud/d/alicloud_resource_manager_control_policy_attachments"

  # language - (optional) is a type of string
  language = null
  # output_file - (optional) is a type of string
  output_file = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # target_id - (required) is a type of string
  target_id = null
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

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_control_policy_attachments" "this" {
  language    = var.language
  output_file = var.output_file
  policy_type = var.policy_type
  target_id   = var.target_id
}
```

[top](#index)

### Outputs

```terraform
output "attachments" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_control_policy_attachments.this.attachments
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_control_policy_attachments.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_control_policy_attachments.this.ids
}

output "this" {
  value = alicloud_resource_manager_control_policy_attachments.this
}
```

[top](#index)