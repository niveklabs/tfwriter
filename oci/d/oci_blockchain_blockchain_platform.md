# oci_blockchain_blockchain_platform

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
module "oci_blockchain_blockchain_platform" {
  source = "./modules/oci/d/oci_blockchain_blockchain_platform"

  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = null
}
```

[top](#index)

### Variables

```terraform
variable "blockchain_platform_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_blockchain_blockchain_platform" "this" {
  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = var.blockchain_platform_id
}
```

[top](#index)

### Outputs

```terraform
output "ca_cert_archive_text" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.ca_cert_archive_text
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.compartment_id
}

output "component_details" {
  description = "returns a list of object"
  value       = data.oci_blockchain_blockchain_platform.this.component_details
}

output "compute_shape" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.compute_shape
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_blockchain_blockchain_platform.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.display_name
}

output "federated_user_id" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.federated_user_id
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_blockchain_blockchain_platform.this.freeform_tags
}

output "host_ocpu_utilization_info" {
  description = "returns a list of object"
  value       = data.oci_blockchain_blockchain_platform.this.host_ocpu_utilization_info
}

output "id" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.id
}

output "idcs_access_token" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.idcs_access_token
  sensitive   = true
}

output "is_byol" {
  description = "returns a bool"
  value       = data.oci_blockchain_blockchain_platform.this.is_byol
}

output "is_multi_ad" {
  description = "returns a bool"
  value       = data.oci_blockchain_blockchain_platform.this.is_multi_ad
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.lifecycle_details
}

output "load_balancer_shape" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.load_balancer_shape
}

output "platform_role" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.platform_role
}

output "platform_shape_type" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.platform_shape_type
}

output "replicas" {
  description = "returns a list of object"
  value       = data.oci_blockchain_blockchain_platform.this.replicas
}

output "service_endpoint" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.service_endpoint
}

output "service_version" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.service_version
}

output "state" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.state
}

output "storage_size_in_tbs" {
  description = "returns a number"
  value       = data.oci_blockchain_blockchain_platform.this.storage_size_in_tbs
}

output "storage_used_in_tbs" {
  description = "returns a number"
  value       = data.oci_blockchain_blockchain_platform.this.storage_used_in_tbs
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_blockchain_blockchain_platform.this.time_updated
}

output "total_ocpu_capacity" {
  description = "returns a number"
  value       = data.oci_blockchain_blockchain_platform.this.total_ocpu_capacity
}

output "this" {
  value = oci_blockchain_blockchain_platform.this
}
```

[top](#index)