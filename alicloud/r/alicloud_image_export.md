# alicloud_image_export

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
module "alicloud_image_export" {
  source = "./modules/alicloud/r/alicloud_image_export"

  # image_id - (required) is a type of string
  image_id = null
  # oss_bucket - (required) is a type of string
  oss_bucket = null
  # oss_prefix - (optional) is a type of string
  oss_prefix = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(required)"
  type        = string
}

variable "oss_bucket" {
  description = "(required)"
  type        = string
}

variable "oss_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_image_export" "this" {
  image_id   = var.image_id
  oss_bucket = var.oss_bucket
  oss_prefix = var.oss_prefix

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_image_export.this.id
}

output "this" {
  value = alicloud_image_export.this
}
```

[top](#index)