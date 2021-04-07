# ecl_imagestorages_image_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_imagestorages_image_v2" {
  source = "./modules/ecl/r/ecl_imagestorages_image_v2"

  # container_format - (required) is a type of string
  container_format = null
  # disk_format - (required) is a type of string
  disk_format = null
  # license_switch - (optional) is a type of string
  license_switch = null
  # local_file_path - (required) is a type of string
  local_file_path = null
  # min_disk_gb - (optional) is a type of number
  min_disk_gb = null
  # min_ram_mb - (optional) is a type of number
  min_ram_mb = null
  # name - (optional) is a type of string
  name = null
  # properties - (optional) is a type of map of string
  properties = {}
  # protected - (optional) is a type of bool
  protected = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of set of string
  tags = []
  # verify_checksum - (optional) is a type of bool
  verify_checksum = null
  # visibility - (optional) is a type of string
  visibility = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "container_format" {
  description = "(required)"
  type        = string
}

variable "disk_format" {
  description = "(required)"
  type        = string
}

variable "license_switch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_file_path" {
  description = "(required)"
  type        = string
}

variable "min_disk_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_ram_mb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "protected" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "verify_checksum" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "ecl_imagestorages_image_v2" "this" {
  # container_format - (required) is a type of string
  container_format = var.container_format
  # disk_format - (required) is a type of string
  disk_format = var.disk_format
  # license_switch - (optional) is a type of string
  license_switch = var.license_switch
  # local_file_path - (required) is a type of string
  local_file_path = var.local_file_path
  # min_disk_gb - (optional) is a type of number
  min_disk_gb = var.min_disk_gb
  # min_ram_mb - (optional) is a type of number
  min_ram_mb = var.min_ram_mb
  # name - (optional) is a type of string
  name = var.name
  # properties - (optional) is a type of map of string
  properties = var.properties
  # protected - (optional) is a type of bool
  protected = var.protected
  # region - (optional) is a type of string
  region = var.region
  # tags - (optional) is a type of set of string
  tags = var.tags
  # verify_checksum - (optional) is a type of bool
  verify_checksum = var.verify_checksum
  # visibility - (optional) is a type of string
  visibility = var.visibility

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "checksum" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.checksum
}

output "created_at" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.created_at
}

output "file" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.file
}

output "id" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = ecl_imagestorages_image_v2.this.metadata
}

output "owner" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.owner
}

output "properties" {
  description = "returns a map of string"
  value       = ecl_imagestorages_image_v2.this.properties
}

output "region" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.region
}

output "schema" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.schema
}

output "size_bytes" {
  description = "returns a number"
  value       = ecl_imagestorages_image_v2.this.size_bytes
}

output "status" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.status
}

output "update_at" {
  description = "returns a string"
  value       = ecl_imagestorages_image_v2.this.update_at
}

output "this" {
  value = ecl_imagestorages_image_v2.this
}
```

[top](#index)