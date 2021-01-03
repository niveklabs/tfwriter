# alicloud_image_share_permission

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
module "alicloud_image_share_permission" {
  source = "./modules/alicloud/r/alicloud_image_share_permission"

  # account_id - (required) is a type of string
  account_id = null
  # image_id - (required) is a type of string
  image_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "image_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_image_share_permission" "this" {
  account_id = var.account_id
  image_id   = var.image_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_image_share_permission.this.id
}

output "this" {
  value = alicloud_image_share_permission.this
}
```

[top](#index)