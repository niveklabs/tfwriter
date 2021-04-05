# alicloud_edas_slb_attachment

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
module "alicloud_edas_slb_attachment" {
  source = "./modules/alicloud/r/alicloud_edas_slb_attachment"

  # app_id - (required) is a type of string
  app_id = null
  # listener_port - (optional) is a type of number
  listener_port = null
  # slb_id - (required) is a type of string
  slb_id = null
  # slb_ip - (required) is a type of string
  slb_ip = null
  # type - (required) is a type of string
  type = null
  # vserver_group_id - (optional) is a type of string
  vserver_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "listener_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slb_id" {
  description = "(required)"
  type        = string
}

variable "slb_ip" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "vserver_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_slb_attachment" "this" {
  app_id           = var.app_id
  listener_port    = var.listener_port
  slb_id           = var.slb_id
  slb_ip           = var.slb_ip
  type             = var.type
  vserver_group_id = var.vserver_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_edas_slb_attachment.this.id
}

output "slb_status" {
  description = "returns a string"
  value       = alicloud_edas_slb_attachment.this.slb_status
}

output "vswitch_id" {
  description = "returns a string"
  value       = alicloud_edas_slb_attachment.this.vswitch_id
}

output "this" {
  value = alicloud_edas_slb_attachment.this
}
```

[top](#index)