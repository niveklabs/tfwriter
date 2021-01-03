# linode_volume

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_volume" {
  source = "./modules/linode/r/linode_volume"

  # label - (required) is a type of string
  label = null
  # linode_id - (optional) is a type of number
  linode_id = null
  # region - (required) is a type of string
  region = null
  # size - (optional) is a type of number
  size = null
  # tags - (optional) is a type of set of string
  tags = []

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required) - The label of the Linode Volume."
  type        = string
}

variable "linode_id" {
  description = "(optional) - The Linode ID where the Volume should be attached."
  type        = number
  default     = null
}

variable "region" {
  description = "(required) - The region where this volume will be deployed."
  type        = string
}

variable "size" {
  description = "(optional) - Size of the Volume in GB"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - An array of tags applied to this object. Tags are for organizational purposes only."
  type        = set(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_volume" "this" {
  label     = var.label
  linode_id = var.linode_id
  region    = var.region
  size      = var.size
  tags      = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "filesystem_path" {
  description = "returns a string"
  value       = linode_volume.this.filesystem_path
}

output "id" {
  description = "returns a string"
  value       = linode_volume.this.id
}

output "linode_id" {
  description = "returns a number"
  value       = linode_volume.this.linode_id
}

output "size" {
  description = "returns a number"
  value       = linode_volume.this.size
}

output "status" {
  description = "returns a string"
  value       = linode_volume.this.status
}

output "this" {
  value = linode_volume.this
}
```

[top](#index)