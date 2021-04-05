# scaleway_instance_image

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
module "scaleway_instance_image" {
  source = "./modules/scaleway/d/scaleway_instance_image"

  # architecture - (optional) is a type of string
  architecture = null
  # image_id - (optional) is a type of string
  image_id = null
  # latest - (optional) is a type of bool
  latest = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "architecture" {
  description = "(optional) - Architecture of the desired image"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional) - ID of the desired image"
  type        = string
  default     = null
}

variable "latest" {
  description = "(optional) - Select most recent image if multiple match"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Exact name of the desired image"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
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
data "scaleway_instance_image" "this" {
  architecture = var.architecture
  image_id     = var.image_id
  latest       = var.latest
  name         = var.name
  project_id   = var.project_id
  zone         = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "additional_volume_ids" {
  description = "returns a list of string"
  value       = data.scaleway_instance_image.this.additional_volume_ids
}

output "creation_date" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.creation_date
}

output "default_bootscript_id" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.default_bootscript_id
}

output "from_server_id" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.from_server_id
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.id
}

output "modification_date" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.modification_date
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.project_id
}

output "public" {
  description = "returns a bool"
  value       = data.scaleway_instance_image.this.public
}

output "root_volume_id" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.root_volume_id
}

output "state" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.state
}

output "zone" {
  description = "returns a string"
  value       = data.scaleway_instance_image.this.zone
}

output "this" {
  value = scaleway_instance_image.this
}
```

[top](#index)