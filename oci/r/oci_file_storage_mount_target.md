# oci_file_storage_mount_target

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
module "oci_file_storage_mount_target" {
  source = "./modules/oci/r/oci_file_storage_mount_target"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hostname_label - (optional) is a type of string
  hostname_label = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # subnet_id - (required) is a type of string
  subnet_id = null

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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

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

variable "hostname_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
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
resource "oci_file_storage_mount_target" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags
  hostname_label      = var.hostname_label
  ip_address          = var.ip_address
  nsg_ids             = var.nsg_ids
  subnet_id           = var.subnet_id

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_file_storage_mount_target.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.display_name
}

output "export_set_id" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.export_set_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_file_storage_mount_target.this.freeform_tags
}

output "hostname_label" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.hostname_label
}

output "id" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.ip_address
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.lifecycle_details
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_file_storage_mount_target.this.nsg_ids
}

output "private_ip_ids" {
  description = "returns a list of string"
  value       = oci_file_storage_mount_target.this.private_ip_ids
}

output "state" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_file_storage_mount_target.this.time_created
}

output "this" {
  value = oci_file_storage_mount_target.this
}
```

[top](#index)