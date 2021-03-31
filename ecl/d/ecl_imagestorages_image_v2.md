# ecl_imagestorages_image_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_imagestorages_image_v2" {
  source = "./modules/ecl/d/ecl_imagestorages_image_v2"

  # member_status - (optional) is a type of string
  member_status = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # owner - (optional) is a type of string
  owner = null
  # properties - (optional) is a type of map of string
  properties = {}
  # region - (optional) is a type of string
  region = null
  # size_max - (optional) is a type of number
  size_max = null
  # size_min - (optional) is a type of number
  size_min = null
  # sort_direction - (optional) is a type of string
  sort_direction = null
  # sort_key - (optional) is a type of string
  sort_key = null
  # tag - (optional) is a type of string
  tag = null
  # visibility - (optional) is a type of string
  visibility = null
}
```

[top](#index)

### Variables

```terraform
variable "member_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "size_min" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sort_direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_imagestorages_image_v2" "this" {
  member_status  = var.member_status
  most_recent    = var.most_recent
  name           = var.name
  owner          = var.owner
  properties     = var.properties
  region         = var.region
  size_max       = var.size_max
  size_min       = var.size_min
  sort_direction = var.sort_direction
  sort_key       = var.sort_key
  tag            = var.tag
  visibility     = var.visibility
}
```

[top](#index)

### Outputs

```terraform
output "checksum" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.checksum
}

output "container_format" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.container_format
}

output "created_at" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.created_at
}

output "disk_format" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.disk_format
}

output "file" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.file
}

output "id" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.id
}

output "member_status" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.member_status
}

output "metadata" {
  description = "returns a map of string"
  value       = data.ecl_imagestorages_image_v2.this.metadata
}

output "min_disk_gb" {
  description = "returns a number"
  value       = data.ecl_imagestorages_image_v2.this.min_disk_gb
}

output "min_ram_mb" {
  description = "returns a number"
  value       = data.ecl_imagestorages_image_v2.this.min_ram_mb
}

output "name" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.name
}

output "owner" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.owner
}

output "properties" {
  description = "returns a map of string"
  value       = data.ecl_imagestorages_image_v2.this.properties
}

output "protected" {
  description = "returns a bool"
  value       = data.ecl_imagestorages_image_v2.this.protected
}

output "region" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.region
}

output "schema" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.schema
}

output "size_bytes" {
  description = "returns a number"
  value       = data.ecl_imagestorages_image_v2.this.size_bytes
}

output "tag" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.tag
}

output "updated_at" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.updated_at
}

output "visibility" {
  description = "returns a string"
  value       = data.ecl_imagestorages_image_v2.this.visibility
}

output "this" {
  value = ecl_imagestorages_image_v2.this
}
```

[top](#index)