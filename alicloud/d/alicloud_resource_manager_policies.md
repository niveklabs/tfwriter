# alicloud_resource_manager_policies

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
module "alicloud_resource_manager_policies" {
  source = "./modules/alicloud/d/alicloud_resource_manager_policies"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # policy_type - (optional) is a type of string
  policy_type = null
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

variable "name_regex" {
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_policies" "this" {
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
  policy_type = var.policy_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_policies.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_policies.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_policies.this.names
}

output "policies" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_policies.this.policies
}

output "this" {
  value = alicloud_resource_manager_policies.this
}
```

[top](#index)