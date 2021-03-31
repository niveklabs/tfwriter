# oci_golden_gate_deployment

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
module "oci_golden_gate_deployment" {
  source = "./modules/oci/d/oci_golden_gate_deployment"

  # deployment_id - (required) is a type of string
  deployment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_golden_gate_deployment" "this" {
  deployment_id = var.deployment_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.compartment_id
}

output "cpu_core_count" {
  description = "returns a number"
  value       = data.oci_golden_gate_deployment.this.cpu_core_count
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_deployment.this.defined_tags
}

output "deployment_backup_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.deployment_backup_id
}

output "deployment_type" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.deployment_type
}

output "deployment_url" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.deployment_url
}

output "description" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.display_name
}

output "fqdn" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_deployment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.id
}

output "is_auto_scaling_enabled" {
  description = "returns a bool"
  value       = data.oci_golden_gate_deployment.this.is_auto_scaling_enabled
}

output "is_healthy" {
  description = "returns a bool"
  value       = data.oci_golden_gate_deployment.this.is_healthy
}

output "is_latest_version" {
  description = "returns a bool"
  value       = data.oci_golden_gate_deployment.this.is_latest_version
}

output "is_public" {
  description = "returns a bool"
  value       = data.oci_golden_gate_deployment.this.is_public
}

output "license_model" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.license_model
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.lifecycle_details
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_golden_gate_deployment.this.nsg_ids
}

output "ogg_data" {
  description = "returns a list of object"
  value       = data.oci_golden_gate_deployment.this.ogg_data
}

output "private_ip_address" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.private_ip_address
}

output "public_ip_address" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.public_ip_address
}

output "state" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.subnet_id
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_golden_gate_deployment.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_golden_gate_deployment.this.time_updated
}

output "this" {
  value = oci_golden_gate_deployment.this
}
```

[top](#index)