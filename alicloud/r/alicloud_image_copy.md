# alicloud_image_copy

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
module "alicloud_image_copy" {
  source = "./modules/alicloud/r/alicloud_image_copy"

  # description - (optional) is a type of string
  description = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # force - (optional) is a type of bool
  force = null
  # image_name - (optional) is a type of string
  image_name = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (optional) is a type of string
  name = null
  # source_image_id - (required) is a type of string
  source_image_id = null
  # source_region_id - (required) is a type of string
  source_region_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_image_id" {
  description = "(required)"
  type        = string
}

variable "source_region_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_image_copy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # encrypted - (optional) is a type of bool
  encrypted = var.encrypted
  # force - (optional) is a type of bool
  force = var.force
  # image_name - (optional) is a type of string
  image_name = var.image_name
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # name - (optional) is a type of string
  name = var.name
  # source_image_id - (required) is a type of string
  source_image_id = var.source_image_id
  # source_region_id - (required) is a type of string
  source_region_id = var.source_region_id
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_image_copy.this.id
}

output "image_name" {
  description = "returns a string"
  value       = alicloud_image_copy.this.image_name
}

output "name" {
  description = "returns a string"
  value       = alicloud_image_copy.this.name
}

output "this" {
  value = alicloud_image_copy.this
}
```

[top](#index)