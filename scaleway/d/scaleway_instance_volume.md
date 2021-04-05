# scaleway_instance_volume

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/scaleway/d/scaleway_instance_volume"

  # name - (optional) is a type of string
  name = null
  # volume_id - (optional) is a type of string
  volume_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the volume"
  type        = string
  default     = null
}

variable "volume_id" {
  description = "(optional) - The ID of the volume"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_instance_volume" "this" {
  name      = var.name
  volume_id = var.volume_id
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "from_snapshot_id" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.from_snapshot_id
}

output "from_volume_id" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.from_volume_id
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.project_id
}

output "server_id" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.server_id
}

output "size_in_gb" {
  description = "returns a number"
  value       = data.scaleway_instance_volume.this.size_in_gb
}

output "type" {
  description = "returns a string"
  value       = data.scaleway_instance_volume.this.type
}

output "this" {
  value = scaleway_instance_volume.this
}
```

[top](#index)