# vcd_catalog_media

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_catalog_media" {
  source = "./modules/vcd/r/vcd_catalog_media"

  # catalog - (required) is a type of string
  catalog = null
  # description - (optional) is a type of string
  description = null
  # media_path - (required) is a type of string
  media_path = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # show_upload_progress - (optional) is a type of bool
  show_upload_progress = null
  # upload_piece_size - (optional) is a type of number
  upload_piece_size = null
}
```

[top](#index)

### Variables

```terraform
variable "catalog" {
  description = "(required) - catalog name where upload the Media file"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "media_path" {
  description = "(required) - absolute or relative path to Media file"
  type        = string
}

variable "metadata" {
  description = "(optional) - Key and value pairs for catalog item metadata"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - media name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "show_upload_progress" {
  description = "(optional) - shows upload progress in stdout"
  type        = bool
  default     = null
}

variable "upload_piece_size" {
  description = "(optional) - size of upload file piece size in mega bytes"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_catalog_media" "this" {
  # catalog - (required) is a type of string
  catalog = var.catalog
  # description - (optional) is a type of string
  description = var.description
  # media_path - (required) is a type of string
  media_path = var.media_path
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # show_upload_progress - (optional) is a type of bool
  show_upload_progress = var.show_upload_progress
  # upload_piece_size - (optional) is a type of number
  upload_piece_size = var.upload_piece_size
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = vcd_catalog_media.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = vcd_catalog_media.this.id
}

output "is_iso" {
  description = "returns a bool"
  value       = vcd_catalog_media.this.is_iso
}

output "is_published" {
  description = "returns a bool"
  value       = vcd_catalog_media.this.is_published
}

output "owner_name" {
  description = "returns a string"
  value       = vcd_catalog_media.this.owner_name
}

output "size" {
  description = "returns a number"
  value       = vcd_catalog_media.this.size
}

output "status" {
  description = "returns a string"
  value       = vcd_catalog_media.this.status
}

output "storage_profile_name" {
  description = "returns a string"
  value       = vcd_catalog_media.this.storage_profile_name
}

output "this" {
  value = vcd_catalog_media.this
}
```

[top](#index)