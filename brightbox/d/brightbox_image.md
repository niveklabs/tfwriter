# brightbox_image

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_image" {
  source = "./modules/brightbox/d/brightbox_image"

  # ancestor_id - (optional) is a type of string
  ancestor_id = null
  # arch - (optional) is a type of string
  arch = null
  # compatibility_mode - (optional) is a type of bool
  compatibility_mode = null
  # description - (optional) is a type of string
  description = null
  # licence_name - (optional) is a type of string
  licence_name = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # official - (optional) is a type of bool
  official = null
  # owner - (optional) is a type of string
  owner = null
  # public - (optional) is a type of bool
  public = null
  # source_type - (optional) is a type of string
  source_type = null
  # status - (optional) is a type of string
  status = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "ancestor_id" {
  description = "(optional) - Image this image was derived from"
  type        = string
  default     = null
}

variable "arch" {
  description = "(optional) - OS Architecture"
  type        = string
  default     = null
}

variable "compatibility_mode" {
  description = "(optional) - Does this image require a non-virtio VM shell"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - A Description of the image"
  type        = string
  default     = null
}

variable "licence_name" {
  description = "(optional) - The licence name for this image"
  type        = string
  default     = null
}

variable "most_recent" {
  description = "(optional) - Select the most recent image"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - User Label for this image"
  type        = string
  default     = null
}

variable "official" {
  description = "(optional) - Is this image an official Brightbox provided one?"
  type        = bool
  default     = null
}

variable "owner" {
  description = "(optional) - Account ID this image belongs to"
  type        = string
  default     = null
}

variable "public" {
  description = "(optional) - Is this image available to other customers?"
  type        = bool
  default     = null
}

variable "source_type" {
  description = "(optional) - Source type for this image (upload or snapshot)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - State of the image"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional) - Username to use when logging into a server booted with this image"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "brightbox_image" "this" {
  ancestor_id        = var.ancestor_id
  arch               = var.arch
  compatibility_mode = var.compatibility_mode
  description        = var.description
  licence_name       = var.licence_name
  most_recent        = var.most_recent
  name               = var.name
  official           = var.official
  owner              = var.owner
  public             = var.public
  source_type        = var.source_type
  status             = var.status
  username           = var.username
}
```

[top](#index)

### Outputs

```terraform
output "ancestor_id" {
  description = "returns a string"
  value       = data.brightbox_image.this.ancestor_id
}

output "arch" {
  description = "returns a string"
  value       = data.brightbox_image.this.arch
}

output "compatibility_mode" {
  description = "returns a bool"
  value       = data.brightbox_image.this.compatibility_mode
}

output "created_at" {
  description = "returns a string"
  value       = data.brightbox_image.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.brightbox_image.this.description
}

output "disk_size" {
  description = "returns a number"
  value       = data.brightbox_image.this.disk_size
}

output "id" {
  description = "returns a string"
  value       = data.brightbox_image.this.id
}

output "licence_name" {
  description = "returns a string"
  value       = data.brightbox_image.this.licence_name
}

output "locked" {
  description = "returns a bool"
  value       = data.brightbox_image.this.locked
}

output "name" {
  description = "returns a string"
  value       = data.brightbox_image.this.name
}

output "official" {
  description = "returns a bool"
  value       = data.brightbox_image.this.official
}

output "owner" {
  description = "returns a string"
  value       = data.brightbox_image.this.owner
}

output "public" {
  description = "returns a bool"
  value       = data.brightbox_image.this.public
}

output "source_type" {
  description = "returns a string"
  value       = data.brightbox_image.this.source_type
}

output "status" {
  description = "returns a string"
  value       = data.brightbox_image.this.status
}

output "username" {
  description = "returns a string"
  value       = data.brightbox_image.this.username
}

output "virtual_size" {
  description = "returns a number"
  value       = data.brightbox_image.this.virtual_size
}

output "this" {
  value = brightbox_image.this
}
```

[top](#index)