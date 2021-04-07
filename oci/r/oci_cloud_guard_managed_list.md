# oci_cloud_guard_managed_list

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
module "oci_cloud_guard_managed_list" {
  source = "./modules/oci/r/oci_cloud_guard_managed_list"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # list_items - (optional) is a type of list of string
  list_items = []
  # list_type - (optional) is a type of string
  list_type = null
  # source_managed_list_id - (optional) is a type of string
  source_managed_list_id = null

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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "list_items" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "list_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_managed_list_id" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_cloud_guard_managed_list" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # list_items - (optional) is a type of list of string
  list_items = var.list_items
  # list_type - (optional) is a type of string
  list_type = var.list_type
  # source_managed_list_id - (optional) is a type of string
  source_managed_list_id = var.source_managed_list_id

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_managed_list.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.description
}

output "feed_provider" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.feed_provider
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_managed_list.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.id
}

output "is_editable" {
  description = "returns a bool"
  value       = oci_cloud_guard_managed_list.this.is_editable
}

output "lifecyle_details" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.lifecyle_details
}

output "list_items" {
  description = "returns a list of string"
  value       = oci_cloud_guard_managed_list.this.list_items
}

output "list_type" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.list_type
}

output "source_managed_list_id" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.source_managed_list_id
}

output "state" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_managed_list.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_cloud_guard_managed_list.this.time_updated
}

output "this" {
  value = oci_cloud_guard_managed_list.this
}
```

[top](#index)