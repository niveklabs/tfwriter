# profitbricks_volume

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_volume" {
  source = "./modules/profitbricks/r/profitbricks_volume"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # bus - (optional) is a type of string
  bus = null
  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # disk_type - (required) is a type of string
  disk_type = null
  # image_name - (optional) is a type of string
  image_name = null
  # image_password - (optional) is a type of string
  image_password = null
  # licence_type - (optional) is a type of string
  licence_type = null
  # name - (optional) is a type of string
  name = null
  # server_id - (required) is a type of string
  server_id = null
  # size - (required) is a type of number
  size = null
  # ssh_key_path - (optional) is a type of list of string
  ssh_key_path = []

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bus" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datacenter_id" {
  description = "(required)"
  type        = string
}

variable "disk_type" {
  description = "(required)"
  type        = string
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "licence_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "ssh_key_path" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_volume" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # bus - (optional) is a type of string
  bus = var.bus
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
  # disk_type - (required) is a type of string
  disk_type = var.disk_type
  # image_name - (optional) is a type of string
  image_name = var.image_name
  # image_password - (optional) is a type of string
  image_password = var.image_password
  # licence_type - (optional) is a type of string
  licence_type = var.licence_type
  # name - (optional) is a type of string
  name = var.name
  # server_id - (required) is a type of string
  server_id = var.server_id
  # size - (required) is a type of number
  size = var.size
  # ssh_key_path - (optional) is a type of list of string
  ssh_key_path = var.ssh_key_path

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_volume.this.id
}

output "sshkey" {
  description = "returns a string"
  value       = profitbricks_volume.this.sshkey
}

output "this" {
  value = profitbricks_volume.this
}
```

[top](#index)