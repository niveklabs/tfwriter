# alicloud_key_pair

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
module "alicloud_key_pair" {
  source = "./modules/alicloud/r/alicloud_key_pair"

  # key_file - (optional) is a type of string
  key_file = null
  # key_name - (optional) is a type of string
  key_name = null
  # key_name_prefix - (optional) is a type of string
  key_name_prefix = null
  # public_key - (optional) is a type of string
  public_key = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "key_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
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

### Resource

```terraform
resource "alicloud_key_pair" "this" {
  key_file          = var.key_file
  key_name          = var.key_name
  key_name_prefix   = var.key_name_prefix
  public_key        = var.public_key
  resource_group_id = var.resource_group_id
  tags              = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "finger_print" {
  description = "returns a string"
  value       = alicloud_key_pair.this.finger_print
}

output "id" {
  description = "returns a string"
  value       = alicloud_key_pair.this.id
}

output "key_name" {
  description = "returns a string"
  value       = alicloud_key_pair.this.key_name
}

output "this" {
  value = alicloud_key_pair.this
}
```

[top](#index)