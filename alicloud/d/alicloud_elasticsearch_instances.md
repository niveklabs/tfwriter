# alicloud_elasticsearch_instances

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
module "alicloud_elasticsearch_instances" {
  source = "./modules/alicloud/d/alicloud_elasticsearch_instances"

  # description_regex - (optional) is a type of string
  description_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "description_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
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

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_elasticsearch_instances" "this" {
  # description_regex - (optional) is a type of string
  description_regex = var.description_regex
  # ids - (optional) is a type of list of string
  ids = var.ids
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
  # version - (optional) is a type of string
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "descriptions" {
  description = "returns a list of string"
  value       = data.alicloud_elasticsearch_instances.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_elasticsearch_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_elasticsearch_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_elasticsearch_instances.this.instances
}

output "this" {
  value = alicloud_elasticsearch_instances.this
}
```

[top](#index)