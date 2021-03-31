# alicloud_ots_instance_attachment

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ots_instance_attachment" {
  source = "./modules/alicloud/r/alicloud_ots_instance_attachment"

  # instance_name - (required) is a type of string
  instance_name = null
  # vpc_name - (required) is a type of string
  vpc_name = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "vpc_name" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ots_instance_attachment" "this" {
  instance_name = var.instance_name
  vpc_name      = var.vpc_name
  vswitch_id    = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ots_instance_attachment.this.id
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_ots_instance_attachment.this.vpc_id
}

output "this" {
  value = alicloud_ots_instance_attachment.this
}
```

[top](#index)