# alicloud_oss_bucket_objects

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
module "alicloud_oss_bucket_objects" {
  source = "./modules/alicloud/d/alicloud_oss_bucket_objects"

  # bucket_name - (required) is a type of string
  bucket_name = null
  # key_prefix - (optional) is a type of string
  key_prefix = null
  # key_regex - (optional) is a type of string
  key_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket_name" {
  description = "(required)"
  type        = string
}

variable "key_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_regex" {
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
data "alicloud_oss_bucket_objects" "this" {
  bucket_name = var.bucket_name
  key_prefix  = var.key_prefix
  key_regex   = var.key_regex
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_oss_bucket_objects.this.id
}

output "objects" {
  description = "returns a list of object"
  value       = data.alicloud_oss_bucket_objects.this.objects
}

output "this" {
  value = alicloud_oss_bucket_objects.this
}
```

[top](#index)