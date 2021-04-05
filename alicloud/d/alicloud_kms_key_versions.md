# alicloud_kms_key_versions

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
module "alicloud_kms_key_versions" {
  source = "./modules/alicloud/d/alicloud_kms_key_versions"

  # ids - (optional) is a type of list of string
  ids = []
  # key_id - (required) is a type of string
  key_id = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "key_id" {
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
data "alicloud_kms_key_versions" "this" {
  ids         = var.ids
  key_id      = var.key_id
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_kms_key_versions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_kms_key_versions.this.ids
}

output "versions" {
  description = "returns a list of object"
  value       = data.alicloud_kms_key_versions.this.versions
}

output "this" {
  value = alicloud_kms_key_versions.this
}
```

[top](#index)