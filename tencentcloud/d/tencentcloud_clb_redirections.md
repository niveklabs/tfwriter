# tencentcloud_clb_redirections

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
module "tencentcloud_clb_redirections" {
  source = "./modules/tencentcloud/d/tencentcloud_clb_redirections"

  # clb_id - (required) is a type of string
  clb_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # source_listener_id - (required) is a type of string
  source_listener_id = null
  # source_rule_id - (required) is a type of string
  source_rule_id = null
  # target_listener_id - (optional) is a type of string
  target_listener_id = null
  # target_rule_id - (optional) is a type of string
  target_rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - ID of the CLB to be queried."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "source_listener_id" {
  description = "(required) - ID of source listener to be queried."
  type        = string
}

variable "source_rule_id" {
  description = "(required) - Rule ID of source listener to be queried."
  type        = string
}

variable "target_listener_id" {
  description = "(optional) - ID of target listener to be queried."
  type        = string
  default     = null
}

variable "target_rule_id" {
  description = "(optional) - Rule ID of target listener to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_clb_redirections" "this" {
  clb_id             = var.clb_id
  result_output_file = var.result_output_file
  source_listener_id = var.source_listener_id
  source_rule_id     = var.source_rule_id
  target_listener_id = var.target_listener_id
  target_rule_id     = var.target_rule_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_clb_redirections.this.id
}

output "redirection_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_clb_redirections.this.redirection_list
}

output "this" {
  value = tencentcloud_clb_redirections.this
}
```

[top](#index)