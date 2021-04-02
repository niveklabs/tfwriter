# oci_core_image

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_image" {
  source = "./modules/oci/r/oci_core_image"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # instance_id - (optional) is a type of string
  instance_id = null
  # launch_mode - (optional) is a type of string
  launch_mode = null

  image_source_details = [{
    bucket_name              = null
    namespace_name           = null
    object_name              = null
    operating_system         = null
    operating_system_version = null
    source_image_type        = null
    source_type              = null
    source_uri               = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_source_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket_name              = string
      namespace_name           = string
      object_name              = string
      operating_system         = string
      operating_system_version = string
      source_image_type        = string
      source_type              = string
      source_uri               = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_image" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  instance_id    = var.instance_id
  launch_mode    = var.launch_mode

  dynamic "image_source_details" {
    for_each = var.image_source_details
    content {
      bucket_name              = image_source_details.value["bucket_name"]
      namespace_name           = image_source_details.value["namespace_name"]
      object_name              = image_source_details.value["object_name"]
      operating_system         = image_source_details.value["operating_system"]
      operating_system_version = image_source_details.value["operating_system_version"]
      source_image_type        = image_source_details.value["source_image_type"]
      source_type              = image_source_details.value["source_type"]
      source_uri               = image_source_details.value["source_uri"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "agent_features" {
  description = "returns a list of object"
  value       = oci_core_image.this.agent_features
}

output "base_image_id" {
  description = "returns a string"
  value       = oci_core_image.this.base_image_id
}

output "create_image_allowed" {
  description = "returns a bool"
  value       = oci_core_image.this.create_image_allowed
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_image.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_image.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_image.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_image.this.id
}

output "launch_mode" {
  description = "returns a string"
  value       = oci_core_image.this.launch_mode
}

output "launch_options" {
  description = "returns a list of object"
  value       = oci_core_image.this.launch_options
}

output "listing_type" {
  description = "returns a string"
  value       = oci_core_image.this.listing_type
}

output "operating_system" {
  description = "returns a string"
  value       = oci_core_image.this.operating_system
}

output "operating_system_version" {
  description = "returns a string"
  value       = oci_core_image.this.operating_system_version
}

output "size_in_mbs" {
  description = "returns a string"
  value       = oci_core_image.this.size_in_mbs
}

output "state" {
  description = "returns a string"
  value       = oci_core_image.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_image.this.time_created
}

output "this" {
  value = oci_core_image.this
}
```

[top](#index)