# tencentcloud_cam_policies

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
module "tencentcloud_cam_policies" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_policies"

  # create_mode - (optional) is a type of number
  create_mode = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # policy_id - (optional) is a type of string
  policy_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # type - (optional) is a type of number
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "create_mode" {
  description = "(optional) - Mode of creation of policy strategy. Valid values: `1`, `2`. `1` means policy was created with console, and `2` means it was created by strategies."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The description of the CAM policy."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the CAM policy to be queried."
  type        = string
  default     = null
}

variable "policy_id" {
  description = "(optional) - ID of CAM policy to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of the policy strategy. Valid values: `1`, `2`. `1` means customer strategy and `2` means preset strategy."
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cam_policies" "this" {
  create_mode        = var.create_mode
  description        = var.description
  name               = var.name
  policy_id          = var.policy_id
  result_output_file = var.result_output_file
  type               = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_policies.this.id
}

output "policy_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_policies.this.policy_list
}

output "this" {
  value = tencentcloud_cam_policies.this
}
```

[top](#index)