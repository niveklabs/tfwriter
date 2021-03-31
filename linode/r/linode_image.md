# linode_image

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
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_image" {
  source = "./modules/linode/r/linode_image"

  # description - (optional) is a type of string
  description = null
  # disk_id - (required) is a type of number
  disk_id = null
  # label - (required) is a type of string
  label = null
  # linode_id - (required) is a type of number
  linode_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A detailed description of this Image."
  type        = string
  default     = null
}

variable "disk_id" {
  description = "(required) - The ID of the Linode Disk that this Image will be created from."
  type        = number
}

variable "label" {
  description = "(required) - A short description of the Image. Labels cannot contain special characters."
  type        = string
}

variable "linode_id" {
  description = "(required) - The ID of the Linode that this Image will be created from."
  type        = number
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_image" "this" {
  description = var.description
  disk_id     = var.disk_id
  label       = var.label
  linode_id   = var.linode_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = linode_image.this.created
}

output "created_by" {
  description = "returns a string"
  value       = linode_image.this.created_by
}

output "deprecated" {
  description = "returns a bool"
  value       = linode_image.this.deprecated
}

output "expiry" {
  description = "returns a string"
  value       = linode_image.this.expiry
}

output "id" {
  description = "returns a string"
  value       = linode_image.this.id
}

output "is_public" {
  description = "returns a bool"
  value       = linode_image.this.is_public
}

output "size" {
  description = "returns a number"
  value       = linode_image.this.size
}

output "type" {
  description = "returns a string"
  value       = linode_image.this.type
}

output "vendor" {
  description = "returns a string"
  value       = linode_image.this.vendor
}

output "this" {
  value = linode_image.this
}
```

[top](#index)