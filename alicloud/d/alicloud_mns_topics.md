# alicloud_mns_topics

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
module "alicloud_mns_topics" {
  source = "./modules/alicloud/d/alicloud_mns_topics"

  # name_prefix - (optional) is a type of string
  name_prefix = null
  # output_file - (optional) is a type of string
  output_file = null
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_mns_topics" "this" {
  name_prefix = var.name_prefix
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_mns_topics.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_mns_topics.this.names
}

output "topics" {
  description = "returns a list of object"
  value       = data.alicloud_mns_topics.this.topics
}

output "this" {
  value = alicloud_mns_topics.this
}
```

[top](#index)