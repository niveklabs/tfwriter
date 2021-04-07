# alicloud_cen_instance_attachment

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
module "alicloud_cen_instance_attachment" {
  source = "./modules/alicloud/r/alicloud_cen_instance_attachment"

  # cen_owner_id - (optional) is a type of number
  cen_owner_id = null
  # child_instance_id - (required) is a type of string
  child_instance_id = null
  # child_instance_owner_id - (optional) is a type of number
  child_instance_owner_id = null
  # child_instance_region_id - (required) is a type of string
  child_instance_region_id = null
  # child_instance_type - (required) is a type of string
  child_instance_type = null
  # instance_id - (required) is a type of string
  instance_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cen_owner_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "child_instance_id" {
  description = "(required)"
  type        = string
}

variable "child_instance_owner_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "child_instance_region_id" {
  description = "(required)"
  type        = string
}

variable "child_instance_type" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
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
resource "alicloud_cen_instance_attachment" "this" {
  # cen_owner_id - (optional) is a type of number
  cen_owner_id = var.cen_owner_id
  # child_instance_id - (required) is a type of string
  child_instance_id = var.child_instance_id
  # child_instance_owner_id - (optional) is a type of number
  child_instance_owner_id = var.child_instance_owner_id
  # child_instance_region_id - (required) is a type of string
  child_instance_region_id = var.child_instance_region_id
  # child_instance_type - (required) is a type of string
  child_instance_type = var.child_instance_type
  # instance_id - (required) is a type of string
  instance_id = var.instance_id

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
output "child_instance_owner_id" {
  description = "returns a number"
  value       = alicloud_cen_instance_attachment.this.child_instance_owner_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_cen_instance_attachment.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_cen_instance_attachment.this.status
}

output "this" {
  value = alicloud_cen_instance_attachment.this
}
```

[top](#index)