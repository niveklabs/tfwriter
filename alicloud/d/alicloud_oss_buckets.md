# alicloud_oss_buckets

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
module "alicloud_oss_buckets" {
  source = "./modules/alicloud/d/alicloud_oss_buckets"

  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_oss_buckets" "this" {
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "buckets" {
  description = "returns a list of object"
  value       = data.alicloud_oss_buckets.this.buckets
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_oss_buckets.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_oss_buckets.this.names
}

output "this" {
  value = alicloud_oss_buckets.this
}
```

[top](#index)