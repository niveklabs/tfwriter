# alicloud_disk_attachment

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
module "alicloud_disk_attachment" {
  source = "./modules/alicloud/r/alicloud_disk_attachment"

  # device_name - (optional) is a type of string
  device_name = null
  # disk_id - (required) is a type of string
  disk_id = null
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "device_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_id" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_disk_attachment" "this" {
  # device_name - (optional) is a type of string
  device_name = var.device_name
  # disk_id - (required) is a type of string
  disk_id = var.disk_id
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "device_name" {
  description = "returns a string"
  value       = alicloud_disk_attachment.this.device_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_disk_attachment.this.id
}

output "this" {
  value = alicloud_disk_attachment.this
}
```

[top](#index)