# oci_core_volume

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
module "oci_core_volume" {
  source = "./modules/oci/d/oci_core_volume"

  # volume_id - (required) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "volume_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_volume" "this" {
  volume_id = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "auto_tuned_vpus_per_gb" {
  description = "returns a string"
  value       = data.oci_core_volume.this.auto_tuned_vpus_per_gb
}

output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_volume.this.availability_domain
}

output "backup_policy_id" {
  description = "returns a string"
  value       = data.oci_core_volume.this.backup_policy_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_volume.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_volume.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_volume.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_volume.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_volume.this.id
}

output "is_auto_tune_enabled" {
  description = "returns a bool"
  value       = data.oci_core_volume.this.is_auto_tune_enabled
}

output "is_hydrated" {
  description = "returns a bool"
  value       = data.oci_core_volume.this.is_hydrated
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.oci_core_volume.this.kms_key_id
}

output "size_in_gbs" {
  description = "returns a string"
  value       = data.oci_core_volume.this.size_in_gbs
}

output "size_in_mbs" {
  description = "returns a string"
  value       = data.oci_core_volume.this.size_in_mbs
}

output "source_details" {
  description = "returns a list of object"
  value       = data.oci_core_volume.this.source_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_volume.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_core_volume.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_volume.this.time_created
}

output "volume_backup_id" {
  description = "returns a string"
  value       = data.oci_core_volume.this.volume_backup_id
}

output "volume_group_id" {
  description = "returns a string"
  value       = data.oci_core_volume.this.volume_group_id
}

output "vpus_per_gb" {
  description = "returns a string"
  value       = data.oci_core_volume.this.vpus_per_gb
}

output "this" {
  value = oci_core_volume.this
}
```

[top](#index)