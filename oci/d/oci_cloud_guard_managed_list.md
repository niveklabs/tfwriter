# oci_cloud_guard_managed_list

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/oci/d/oci_cloud_guard_managed_list"

  # managed_list_id - (required) is a type of string
  managed_list_id = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_list_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_cloud_guard_managed_list" "this" {
  # managed_list_id - (required) is a type of string
  managed_list_id = var.managed_list_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_managed_list.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.display_name
}

output "feed_provider" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.feed_provider
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_managed_list.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.id
}

output "is_editable" {
  description = "returns a bool"
  value       = data.oci_cloud_guard_managed_list.this.is_editable
}

output "lifecyle_details" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.lifecyle_details
}

output "list_items" {
  description = "returns a list of string"
  value       = data.oci_cloud_guard_managed_list.this.list_items
}

output "list_type" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.list_type
}

output "source_managed_list_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.source_managed_list_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_managed_list.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_cloud_guard_managed_list.this.time_updated
}

output "this" {
  value = oci_cloud_guard_managed_list.this
}
```

[top](#index)