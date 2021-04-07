# alicloud_kms_key_version

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_key_version" {
  source = "./modules/alicloud/r/alicloud_kms_key_version"

  # key_id - (required) is a type of string
  key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "key_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kms_key_version" "this" {
  # key_id - (required) is a type of string
  key_id = var.key_id
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = alicloud_kms_key_version.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = alicloud_kms_key_version.this.id
}

output "key_version_id" {
  description = "returns a string"
  value       = alicloud_kms_key_version.this.key_version_id
}

output "this" {
  value = alicloud_kms_key_version.this
}
```

[top](#index)