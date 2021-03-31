# nomad_volume

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.13"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_volume" {
  source = "./modules/nomad/r/nomad_volume"

  # access_mode - (required) is a type of string
  access_mode = null
  # attachment_mode - (required) is a type of string
  attachment_mode = null
  # context - (optional) is a type of map of string
  context = {}
  # deregister_on_destroy - (optional) is a type of bool
  deregister_on_destroy = null
  # external_id - (required) is a type of string
  external_id = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # plugin_id - (required) is a type of string
  plugin_id = null
  # secrets - (optional) is a type of map of string
  secrets = {}
  # type - (optional) is a type of string
  type = null
  # volume_id - (required) is a type of string
  volume_id = null

  mount_options = [{
    fs_type     = null
    mount_flags = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_mode" {
  description = "(required) - Defines whether a volume should be available concurrently."
  type        = string
}

variable "attachment_mode" {
  description = "(required) - The storage API that will be used by the volume."
  type        = string
}

variable "context" {
  description = "(optional) - An optional key-value map of strings passed directly to the CSI plugin to validate the volume."
  type        = map(string)
  default     = null
}

variable "deregister_on_destroy" {
  description = "(optional) - If true, the volume will be deregistered on destroy."
  type        = bool
  default     = null
}

variable "external_id" {
  description = "(required) - The ID of the physical volume from the storage provider."
  type        = string
}

variable "name" {
  description = "(required) - The display name of the volume."
  type        = string
}

variable "namespace" {
  description = "(optional) - The namespace in which to create the volume."
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional) - An optional key-value map of strings passed directly to the CSI plugin to configure the volume."
  type        = map(string)
  default     = null
}

variable "plugin_id" {
  description = "(required) - The ID of the CSI plugin that manages this volume."
  type        = string
}

variable "secrets" {
  description = "(optional) - An optional key-value map of strings used as credentials for publishing and unpublishing volumes."
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - The type of the volume. Currently, only 'csi' is supported."
  type        = string
  default     = null
}

variable "volume_id" {
  description = "(required) - The unique ID of the volume, how jobs will refer to the volume."
  type        = string
}

variable "mount_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fs_type     = string
      mount_flags = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nomad_volume" "this" {
  access_mode           = var.access_mode
  attachment_mode       = var.attachment_mode
  context               = var.context
  deregister_on_destroy = var.deregister_on_destroy
  external_id           = var.external_id
  name                  = var.name
  namespace             = var.namespace
  parameters            = var.parameters
  plugin_id             = var.plugin_id
  secrets               = var.secrets
  type                  = var.type
  volume_id             = var.volume_id

  dynamic "mount_options" {
    for_each = var.mount_options
    content {
      fs_type     = mount_options.value["fs_type"]
      mount_flags = mount_options.value["mount_flags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "controller_required" {
  description = "returns a bool"
  value       = nomad_volume.this.controller_required
}

output "controllers_expected" {
  description = "returns a number"
  value       = nomad_volume.this.controllers_expected
}

output "controllers_healthy" {
  description = "returns a number"
  value       = nomad_volume.this.controllers_healthy
}

output "id" {
  description = "returns a string"
  value       = nomad_volume.this.id
}

output "nodes_expected" {
  description = "returns a number"
  value       = nomad_volume.this.nodes_expected
}

output "nodes_healthy" {
  description = "returns a number"
  value       = nomad_volume.this.nodes_healthy
}

output "plugin_provider" {
  description = "returns a string"
  value       = nomad_volume.this.plugin_provider
}

output "plugin_provider_version" {
  description = "returns a string"
  value       = nomad_volume.this.plugin_provider_version
}

output "schedulable" {
  description = "returns a bool"
  value       = nomad_volume.this.schedulable
}

output "this" {
  value = nomad_volume.this
}
```

[top](#index)