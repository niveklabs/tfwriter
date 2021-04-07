# oci_core_boot_volume_replica

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
module "oci_core_boot_volume_replica" {
  source = "./modules/oci/d/oci_core_boot_volume_replica"

  # boot_volume_replica_id - (required) is a type of string
  boot_volume_replica_id = null
}
```

[top](#index)

### Variables

```terraform
variable "boot_volume_replica_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_boot_volume_replica" "this" {
  boot_volume_replica_id = var.boot_volume_replica_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.availability_domain
}

output "boot_volume_id" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.boot_volume_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_boot_volume_replica.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_boot_volume_replica.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.image_id
}

output "size_in_gbs" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.size_in_gbs
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.time_created
}

output "time_last_synced" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_replica.this.time_last_synced
}

output "this" {
  value = oci_core_boot_volume_replica.this
}
```

[top](#index)