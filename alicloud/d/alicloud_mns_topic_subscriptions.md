# alicloud_mns_topic_subscriptions

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_mns_topic_subscriptions" {
  source = "./modules/alicloud/d/alicloud_mns_topic_subscriptions"

  # name_prefix - (optional) is a type of string
  name_prefix = null
  # output_file - (optional) is a type of string
  output_file = null
  # topic_name - (required) is a type of string
  topic_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "topic_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_mns_topic_subscriptions" "this" {
  name_prefix = var.name_prefix
  output_file = var.output_file
  topic_name  = var.topic_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_mns_topic_subscriptions.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_mns_topic_subscriptions.this.names
}

output "subscriptions" {
  description = "returns a list of object"
  value       = data.alicloud_mns_topic_subscriptions.this.subscriptions
}

output "this" {
  value = alicloud_mns_topic_subscriptions.this
}
```

[top](#index)