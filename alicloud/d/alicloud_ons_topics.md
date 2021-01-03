# alicloud_ons_topics

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ons_topics" {
  source = "./modules/alicloud/d/alicloud_ons_topics"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ons_topics" "this" {
  enable_details = var.enable_details
  ids            = var.ids
  instance_id    = var.instance_id
  name_regex     = var.name_regex
  output_file    = var.output_file
  tags           = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ons_topics.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ons_topics.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ons_topics.this.names
}

output "topics" {
  description = "returns a list of object"
  value       = data.alicloud_ons_topics.this.topics
}

output "this" {
  value = alicloud_ons_topics.this
}
```

[top](#index)