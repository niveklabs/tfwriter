# oci_core_volume_attachment

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_volume_attachment" {
  source = "./modules/oci/r/oci_core_volume_attachment"

  # attachment_type - (required) is a type of string
  attachment_type = null
  # compartment_id - (optional) is a type of string
  compartment_id = null
  # device - (optional) is a type of string
  device = null
  # display_name - (optional) is a type of string
  display_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # is_pv_encryption_in_transit_enabled - (optional) is a type of bool
  is_pv_encryption_in_transit_enabled = null
  # is_read_only - (optional) is a type of bool
  is_read_only = null
  # is_shareable - (optional) is a type of bool
  is_shareable = null
  # use_chap - (optional) is a type of bool
  use_chap = null
  # volume_id - (required) is a type of string
  volume_id = null

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
variable "attachment_type" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "is_pv_encryption_in_transit_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_read_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_shareable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_chap" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "volume_id" {
  description = "(required)"
  type        = string
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
resource "oci_core_volume_attachment" "this" {
  # attachment_type - (required) is a type of string
  attachment_type = var.attachment_type
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # device - (optional) is a type of string
  device = var.device
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # is_pv_encryption_in_transit_enabled - (optional) is a type of bool
  is_pv_encryption_in_transit_enabled = var.is_pv_encryption_in_transit_enabled
  # is_read_only - (optional) is a type of bool
  is_read_only = var.is_read_only
  # is_shareable - (optional) is a type of bool
  is_shareable = var.is_shareable
  # use_chap - (optional) is a type of bool
  use_chap = var.use_chap
  # volume_id - (required) is a type of string
  volume_id = var.volume_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.availability_domain
}

output "chap_secret" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.chap_secret
}

output "chap_username" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.chap_username
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.compartment_id
}

output "device" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.device
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.ipv4
}

output "iqn" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.iqn
}

output "is_pv_encryption_in_transit_enabled" {
  description = "returns a bool"
  value       = oci_core_volume_attachment.this.is_pv_encryption_in_transit_enabled
}

output "is_read_only" {
  description = "returns a bool"
  value       = oci_core_volume_attachment.this.is_read_only
}

output "is_shareable" {
  description = "returns a bool"
  value       = oci_core_volume_attachment.this.is_shareable
}

output "port" {
  description = "returns a number"
  value       = oci_core_volume_attachment.this.port
}

output "state" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_volume_attachment.this.time_created
}

output "use_chap" {
  description = "returns a bool"
  value       = oci_core_volume_attachment.this.use_chap
}

output "this" {
  value = oci_core_volume_attachment.this
}
```

[top](#index)