# alicloud_alikafka_consumer_groups

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_alikafka_consumer_groups" {
  source = "./modules/alicloud/d/alicloud_alikafka_consumer_groups"

  # consumer_id_regex - (optional) is a type of string
  consumer_id_regex = null
  # instance_id - (required) is a type of string
  instance_id = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "consumer_id_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_alikafka_consumer_groups" "this" {
  consumer_id_regex = var.consumer_id_regex
  instance_id       = var.instance_id
  output_file       = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "consumer_ids" {
  description = "returns a list of string"
  value       = data.alicloud_alikafka_consumer_groups.this.consumer_ids
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_alikafka_consumer_groups.this.id
}

output "this" {
  value = alicloud_alikafka_consumer_groups.this
}
```

[top](#index)