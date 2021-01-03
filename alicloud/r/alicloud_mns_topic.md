# alicloud_mns_topic

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_mns_topic" {
  source = "./modules/alicloud/r/alicloud_mns_topic"

  # logging_enabled - (optional) is a type of bool
  logging_enabled = null
  # maximum_message_size - (optional) is a type of number
  maximum_message_size = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "logging_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "maximum_message_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_mns_topic" "this" {
  logging_enabled      = var.logging_enabled
  maximum_message_size = var.maximum_message_size
  name                 = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_mns_topic.this.id
}

output "this" {
  value = alicloud_mns_topic.this
}
```

[top](#index)