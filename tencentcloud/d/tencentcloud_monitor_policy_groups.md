# tencentcloud_monitor_policy_groups

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_monitor_policy_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_monitor_policy_groups"

  # name - (optional) is a type of string
  name = null
  # policy_view_names - (optional) is a type of list of string
  policy_view_names = []
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Policy group name for query."
  type        = string
  default     = null
}

variable "policy_view_names" {
  description = "(optional) - The policy view for query."
  type        = list(string)
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_monitor_policy_groups" "this" {
  # name - (optional) is a type of string
  name = var.name
  # policy_view_names - (optional) is a type of list of string
  policy_view_names = var.policy_view_names
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_monitor_policy_groups.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_monitor_policy_groups.this.list
}

output "this" {
  value = tencentcloud_monitor_policy_groups.this
}
```

[top](#index)