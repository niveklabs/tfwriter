# alicloud_mns_queue

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_mns_queue" {
  source = "./modules/alicloud/r/alicloud_mns_queue"

  # delay_seconds - (optional) is a type of number
  delay_seconds = null
  # maximum_message_size - (optional) is a type of number
  maximum_message_size = null
  # message_retention_period - (optional) is a type of number
  message_retention_period = null
  # name - (required) is a type of string
  name = null
  # polling_wait_seconds - (optional) is a type of number
  polling_wait_seconds = null
  # visibility_timeout - (optional) is a type of number
  visibility_timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "delay_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_message_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "message_retention_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "polling_wait_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "visibility_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_mns_queue" "this" {
  delay_seconds            = var.delay_seconds
  maximum_message_size     = var.maximum_message_size
  message_retention_period = var.message_retention_period
  name                     = var.name
  polling_wait_seconds     = var.polling_wait_seconds
  visibility_timeout       = var.visibility_timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_mns_queue.this.id
}

output "this" {
  value = alicloud_mns_queue.this
}
```

[top](#index)