# oci_core_image

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_image" {
  source = "./modules/oci/d/oci_core_image"

  # image_id - (required) is a type of string
  image_id = null
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_image" "this" {
  image_id = var.image_id
}
```

[top](#index)

### Outputs

```terraform
output "agent_features" {
  description = "returns a list of object"
  value       = data.oci_core_image.this.agent_features
}

output "base_image_id" {
  description = "returns a string"
  value       = data.oci_core_image.this.base_image_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_image.this.compartment_id
}

output "create_image_allowed" {
  description = "returns a bool"
  value       = data.oci_core_image.this.create_image_allowed
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_image.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_image.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_image.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_image.this.id
}

output "image_source_details" {
  description = "returns a list of object"
  value       = data.oci_core_image.this.image_source_details
}

output "instance_id" {
  description = "returns a string"
  value       = data.oci_core_image.this.instance_id
}

output "launch_mode" {
  description = "returns a string"
  value       = data.oci_core_image.this.launch_mode
}

output "launch_options" {
  description = "returns a list of object"
  value       = data.oci_core_image.this.launch_options
}

output "listing_type" {
  description = "returns a string"
  value       = data.oci_core_image.this.listing_type
}

output "operating_system" {
  description = "returns a string"
  value       = data.oci_core_image.this.operating_system
}

output "operating_system_version" {
  description = "returns a string"
  value       = data.oci_core_image.this.operating_system_version
}

output "size_in_mbs" {
  description = "returns a string"
  value       = data.oci_core_image.this.size_in_mbs
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_image.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_image.this.time_created
}

output "this" {
  value = oci_core_image.this
}
```

[top](#index)