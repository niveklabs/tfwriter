# alicloud_key_pair_attachment

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
module "alicloud_key_pair_attachment" {
  source = "./modules/alicloud/r/alicloud_key_pair_attachment"

  # force - (optional) is a type of bool
  force = null
  # instance_ids - (required) is a type of set of string
  instance_ids = []
  # key_name - (required) is a type of string
  key_name = null
}
```

[top](#index)

### Variables

```terraform
variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_ids" {
  description = "(required)"
  type        = set(string)
}

variable "key_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_key_pair_attachment" "this" {
  # force - (optional) is a type of bool
  force = var.force
  # instance_ids - (required) is a type of set of string
  instance_ids = var.instance_ids
  # key_name - (required) is a type of string
  key_name = var.key_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_key_pair_attachment.this.id
}

output "this" {
  value = alicloud_key_pair_attachment.this
}
```

[top](#index)