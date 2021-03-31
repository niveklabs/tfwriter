# oci_integration_integration_instance

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
module "oci_integration_integration_instance" {
  source = "./modules/oci/d/oci_integration_integration_instance"

  # integration_instance_id - (required) is a type of string
  integration_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "integration_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_integration_integration_instance" "this" {
  integration_instance_id = var.integration_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "alternate_custom_endpoints" {
  description = "returns a list of object"
  value       = data.oci_integration_integration_instance.this.alternate_custom_endpoints
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.compartment_id
}

output "consumption_model" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.consumption_model
}

output "custom_endpoint" {
  description = "returns a list of object"
  value       = data.oci_integration_integration_instance.this.custom_endpoint
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_integration_integration_instance.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_integration_integration_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.id
}

output "idcs_at" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.idcs_at
  sensitive   = true
}

output "instance_url" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.instance_url
}

output "integration_instance_type" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.integration_instance_type
}

output "is_byol" {
  description = "returns a bool"
  value       = data.oci_integration_integration_instance.this.is_byol
}

output "is_file_server_enabled" {
  description = "returns a bool"
  value       = data.oci_integration_integration_instance.this.is_file_server_enabled
}

output "is_visual_builder_enabled" {
  description = "returns a bool"
  value       = data.oci_integration_integration_instance.this.is_visual_builder_enabled
}

output "message_packs" {
  description = "returns a number"
  value       = data.oci_integration_integration_instance.this.message_packs
}

output "network_endpoint_details" {
  description = "returns a list of object"
  value       = data.oci_integration_integration_instance.this.network_endpoint_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.state_message
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_integration_integration_instance.this.time_updated
}

output "this" {
  value = oci_integration_integration_instance.this
}
```

[top](#index)