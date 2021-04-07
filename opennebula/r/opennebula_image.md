# opennebula_image

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_image" {
  source = "./modules/opennebula/r/opennebula_image"

  # clone_from_image - (optional) is a type of string
  clone_from_image = null
  # datastore_id - (required) is a type of number
  datastore_id = null
  # description - (optional) is a type of string
  description = null
  # dev_prefix - (optional) is a type of string
  dev_prefix = null
  # driver - (optional) is a type of string
  driver = null
  # format - (optional) is a type of string
  format = null
  # group - (optional) is a type of string
  group = null
  # lock - (optional) is a type of string
  lock = null
  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # permissions - (optional) is a type of string
  permissions = null
  # persistent - (optional) is a type of bool
  persistent = null
  # size - (optional) is a type of number
  size = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target - (optional) is a type of string
  target = null
  # timeout - (optional) is a type of number
  timeout = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "clone_from_image" {
  description = "(optional) - ID or name of the Image to be cloned from"
  type        = string
  default     = null
}

variable "datastore_id" {
  description = "(required) - ID of the datastore where Image will be stored"
  type        = number
}

variable "description" {
  description = "(optional) - Description of the Image, in OpenNebula's XML or String format"
  type        = string
  default     = null
}

variable "dev_prefix" {
  description = "(optional) - Device prefix, normally one of: hd, sd, vd"
  type        = string
  default     = null
}

variable "driver" {
  description = "(optional) - Driver to use, normally 'raw' or 'qcow2'"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional) - Image format, normally 'raw' or 'qcow2'"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional) - Name of the Group that onws the Image, If empty, it uses caller group"
  type        = string
  default     = null
}

variable "lock" {
  description = "(optional) - Lock level of the new Image: USE, MANAGE, ADMIN, ALL, UNLOCK"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the Image"
  type        = string
}

variable "path" {
  description = "(optional) - Path to the new image (local path on the OpenNebula server or URL)"
  type        = string
  default     = null
}

variable "permissions" {
  description = "(optional) - Permissions for the Image (in Unix format, owner-group-other, use-manage-admin)"
  type        = string
  default     = null
}

variable "persistent" {
  description = "(optional) - Flag which indicates if the Image has to be persistent"
  type        = bool
  default     = null
}

variable "size" {
  description = "(optional) - Size of the new image in MB"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}

variable "target" {
  description = "(optional) - Device target, example: vda"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional) - Timeout (in minutes) within resource should be available. Default: 10 minutes"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional) - Type of the new Image: OS, CDROM, DATABLOCK, KERNEL, RAMDISK, CONTEXT"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_image" "this" {
  # clone_from_image - (optional) is a type of string
  clone_from_image = var.clone_from_image
  # datastore_id - (required) is a type of number
  datastore_id = var.datastore_id
  # description - (optional) is a type of string
  description = var.description
  # dev_prefix - (optional) is a type of string
  dev_prefix = var.dev_prefix
  # driver - (optional) is a type of string
  driver = var.driver
  # format - (optional) is a type of string
  format = var.format
  # group - (optional) is a type of string
  group = var.group
  # lock - (optional) is a type of string
  lock = var.lock
  # name - (required) is a type of string
  name = var.name
  # path - (optional) is a type of string
  path = var.path
  # permissions - (optional) is a type of string
  permissions = var.permissions
  # persistent - (optional) is a type of bool
  persistent = var.persistent
  # size - (optional) is a type of number
  size = var.size
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target - (optional) is a type of string
  target = var.target
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = opennebula_image.this.description
}

output "dev_prefix" {
  description = "returns a string"
  value       = opennebula_image.this.dev_prefix
}

output "driver" {
  description = "returns a string"
  value       = opennebula_image.this.driver
}

output "format" {
  description = "returns a string"
  value       = opennebula_image.this.format
}

output "gid" {
  description = "returns a number"
  value       = opennebula_image.this.gid
}

output "gname" {
  description = "returns a string"
  value       = opennebula_image.this.gname
}

output "id" {
  description = "returns a string"
  value       = opennebula_image.this.id
}

output "lock" {
  description = "returns a string"
  value       = opennebula_image.this.lock
}

output "path" {
  description = "returns a string"
  value       = opennebula_image.this.path
}

output "permissions" {
  description = "returns a string"
  value       = opennebula_image.this.permissions
}

output "size" {
  description = "returns a number"
  value       = opennebula_image.this.size
}

output "target" {
  description = "returns a string"
  value       = opennebula_image.this.target
}

output "type" {
  description = "returns a string"
  value       = opennebula_image.this.type
}

output "uid" {
  description = "returns a number"
  value       = opennebula_image.this.uid
}

output "uname" {
  description = "returns a string"
  value       = opennebula_image.this.uname
}

output "this" {
  value = opennebula_image.this
}
```

[top](#index)