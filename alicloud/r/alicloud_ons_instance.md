# alicloud_ons_instance

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
module "alicloud_ons_instance" {
  source = "./modules/alicloud/r/alicloud_ons_instance"

  # instance_name - (optional) is a type of string
  instance_name = null
  # name - (optional) is a type of string
  name = null
  # remark - (optional) is a type of string
  remark = null
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
variable "instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remark" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_ons_instance" "this" {
  instance_name = var.instance_name
  name          = var.name
  remark        = var.remark
  tags          = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
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
  value       = alicloud_ons_instance.this.id
}

output "instance_name" {
  description = "returns a string"
  value       = alicloud_ons_instance.this.instance_name
}

output "instance_status" {
  description = "returns a number"
  value       = alicloud_ons_instance.this.instance_status
}

output "instance_type" {
  description = "returns a number"
  value       = alicloud_ons_instance.this.instance_type
}

output "name" {
  description = "returns a string"
  value       = alicloud_ons_instance.this.name
}

output "release_time" {
  description = "returns a string"
  value       = alicloud_ons_instance.this.release_time
}

output "status" {
  description = "returns a number"
  value       = alicloud_ons_instance.this.status
}

output "this" {
  value = alicloud_ons_instance.this
}
```

[top](#index)