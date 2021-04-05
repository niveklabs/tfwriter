# alicloud_resource_manager_policy_versions

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
module "alicloud_resource_manager_policy_versions" {
  source = "./modules/alicloud/d/alicloud_resource_manager_policy_versions"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # policy_name - (required) is a type of string
  policy_name = null
  # policy_type - (required) is a type of string
  policy_type = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_name" {
  description = "(required)"
  type        = string
}

variable "policy_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_policy_versions" "this" {
  enable_details = var.enable_details
  ids            = var.ids
  output_file    = var.output_file
  policy_name    = var.policy_name
  policy_type    = var.policy_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_policy_versions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_policy_versions.this.ids
}

output "versions" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_policy_versions.this.versions
}

output "this" {
  value = alicloud_resource_manager_policy_versions.this
}
```

[top](#index)