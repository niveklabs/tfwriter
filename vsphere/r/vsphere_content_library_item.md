# vsphere_content_library_item

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_content_library_item" {
  source = "./modules/vsphere/r/vsphere_content_library_item"

  # description - (optional) is a type of string
  description = null
  # file_url - (optional) is a type of string
  file_url = null
  # library_id - (required) is a type of string
  library_id = null
  # name - (required) is a type of string
  name = null
  # source_uuid - (optional) is a type of string
  source_uuid = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Optional description of the content library item."
  type        = string
  default     = null
}

variable "file_url" {
  description = "(optional) - ID of source VM of content library item."
  type        = string
  default     = null
}

variable "library_id" {
  description = "(required) - ID of the content library to contain item"
  type        = string
}

variable "name" {
  description = "(required) - The name of the content library item."
  type        = string
}

variable "source_uuid" {
  description = "(optional) - The managed object ID of an existing VM to be cloned to the content library."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of content library item."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_content_library_item" "this" {
  description = var.description
  file_url    = var.file_url
  library_id  = var.library_id
  name        = var.name
  source_uuid = var.source_uuid
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_content_library_item.this.id
}

output "this" {
  value = vsphere_content_library_item.this
}
```

[top](#index)