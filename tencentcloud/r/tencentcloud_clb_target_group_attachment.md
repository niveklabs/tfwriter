# tencentcloud_clb_target_group_attachment

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_clb_target_group_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_target_group_attachment"

  # clb_id - (required) is a type of string
  clb_id = null
  # listener_id - (required) is a type of string
  listener_id = null
  # rule_id - (optional) is a type of string
  rule_id = null
  # target_group_id - (optional) is a type of string
  target_group_id = null
  # targrt_group_id - (optional) is a type of string
  targrt_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - ID of the CLB."
  type        = string
}

variable "listener_id" {
  description = "(required) - ID of the CLB listener."
  type        = string
}

variable "rule_id" {
  description = "(optional) - ID of the CLB listener rule."
  type        = string
  default     = null
}

variable "target_group_id" {
  description = "(optional) - ID of the CLB target group."
  type        = string
  default     = null
}

variable "targrt_group_id" {
  description = "(optional) - ID of the CLB target group."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_target_group_attachment" "this" {
  clb_id          = var.clb_id
  listener_id     = var.listener_id
  rule_id         = var.rule_id
  target_group_id = var.target_group_id
  targrt_group_id = var.targrt_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_target_group_attachment.this.id
}

output "this" {
  value = tencentcloud_clb_target_group_attachment.this
}
```

[top](#index)