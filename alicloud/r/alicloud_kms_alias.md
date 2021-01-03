# alicloud_kms_alias

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_alias" {
  source = "./modules/alicloud/r/alicloud_kms_alias"

  # alias_name - (required) is a type of string
  alias_name = null
  # key_id - (required) is a type of string
  key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "alias_name" {
  description = "(required)"
  type        = string
}

variable "key_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kms_alias" "this" {
  alias_name = var.alias_name
  key_id     = var.key_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_kms_alias.this.id
}

output "this" {
  value = alicloud_kms_alias.this
}
```

[top](#index)