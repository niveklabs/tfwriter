# tencentcloud_clb_attachments

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
module "tencentcloud_clb_attachments" {
  source = "./modules/tencentcloud/d/tencentcloud_clb_attachments"

  # clb_id - (required) is a type of string
  clb_id = null
  # listener_id - (required) is a type of string
  listener_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # rule_id - (optional) is a type of string
  rule_id = null
}
```

[top](#index)

### Variables

```terraform
variable "clb_id" {
  description = "(required) - ID of the CLB to be queried."
  type        = string
}

variable "listener_id" {
  description = "(required) - ID of the CLB listener to be queried."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(optional) - ID of the CLB listener rule. If the protocol of listener is `HTTP`/`HTTPS`, this para is required."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_clb_attachments" "this" {
  clb_id             = var.clb_id
  listener_id        = var.listener_id
  result_output_file = var.result_output_file
  rule_id            = var.rule_id
}
```

[top](#index)

### Outputs

```terraform
output "attachment_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_clb_attachments.this.attachment_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_clb_attachments.this.id
}

output "this" {
  value = tencentcloud_clb_attachments.this
}
```

[top](#index)