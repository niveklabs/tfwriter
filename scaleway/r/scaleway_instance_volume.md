# scaleway_instance_volume

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_volume" {
  source = "./modules/scaleway/r/scaleway_instance_volume"

  # from_snapshot_id - (optional) is a type of string
  from_snapshot_id = null
  # from_volume_id - (optional) is a type of string
  from_volume_id = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # size_in_gb - (optional) is a type of number
  size_in_gb = null
  # type - (required) is a type of string
  type = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "from_snapshot_id" {
  description = "(optional) - Create a volume based on a image"
  type        = string
  default     = null
}

variable "from_volume_id" {
  description = "(optional) - Create a copy of an existing volume"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the volume"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "size_in_gb" {
  description = "(optional) - The size of the volume in gigabyte"
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - The volume type"
  type        = string
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_instance_volume" "this" {
  from_snapshot_id = var.from_snapshot_id
  from_volume_id   = var.from_volume_id
  name             = var.name
  project_id       = var.project_id
  size_in_gb       = var.size_in_gb
  type             = var.type
  zone             = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_instance_volume.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_instance_volume.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_instance_volume.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_instance_volume.this.project_id
}

output "server_id" {
  description = "returns a string"
  value       = scaleway_instance_volume.this.server_id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_volume.this.zone
}

output "this" {
  value = scaleway_instance_volume.this
}
```

[top](#index)