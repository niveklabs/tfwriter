# alicloud_cen_instance

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
module "alicloud_cen_instance" {
  source = "./modules/alicloud/r/alicloud_cen_instance"

  # cen_instance_name - (optional) is a type of string
  cen_instance_name = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # protection_level - (optional) is a type of string
  protection_level = null
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
variable "cen_instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protection_level" {
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
resource "alicloud_cen_instance" "this" {
  cen_instance_name = var.cen_instance_name
  description       = var.description
  name              = var.name
  protection_level  = var.protection_level
  tags              = var.tags

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
output "cen_instance_name" {
  description = "returns a string"
  value       = alicloud_cen_instance.this.cen_instance_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_cen_instance.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_cen_instance.this.name
}

output "status" {
  description = "returns a string"
  value       = alicloud_cen_instance.this.status
}

output "this" {
  value = alicloud_cen_instance.this
}
```

[top](#index)