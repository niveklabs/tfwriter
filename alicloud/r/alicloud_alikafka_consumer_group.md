# alicloud_alikafka_consumer_group

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
module "alicloud_alikafka_consumer_group" {
  source = "./modules/alicloud/r/alicloud_alikafka_consumer_group"

  # consumer_id - (required) is a type of string
  consumer_id = null
  # instance_id - (required) is a type of string
  instance_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "consumer_id" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alikafka_consumer_group" "this" {
  consumer_id = var.consumer_id
  instance_id = var.instance_id
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_alikafka_consumer_group.this.id
}

output "this" {
  value = alicloud_alikafka_consumer_group.this
}
```

[top](#index)