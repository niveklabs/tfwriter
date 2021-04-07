# tencentcloud_as_scaling_policies

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
module "tencentcloud_as_scaling_policies" {
  source = "./modules/tencentcloud/d/tencentcloud_as_scaling_policies"

  # policy_name - (optional) is a type of string
  policy_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # scaling_group_id - (optional) is a type of string
  scaling_group_id = null
  # scaling_policy_id - (optional) is a type of string
  scaling_policy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_name" {
  description = "(optional) - Scaling policy name."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(optional) - Scaling group ID."
  type        = string
  default     = null
}

variable "scaling_policy_id" {
  description = "(optional) - Scaling policy ID."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_as_scaling_policies" "this" {
  # policy_name - (optional) is a type of string
  policy_name = var.policy_name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # scaling_group_id - (optional) is a type of string
  scaling_group_id = var.scaling_group_id
  # scaling_policy_id - (optional) is a type of string
  scaling_policy_id = var.scaling_policy_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_as_scaling_policies.this.id
}

output "scaling_policy_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_as_scaling_policies.this.scaling_policy_list
}

output "this" {
  value = tencentcloud_as_scaling_policies.this
}
```

[top](#index)