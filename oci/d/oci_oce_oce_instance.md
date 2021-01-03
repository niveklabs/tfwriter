# oci_oce_oce_instance

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_oce_oce_instance" {
  source = "./modules/oci/d/oci_oce_oce_instance"

  # oce_instance_id - (required) is a type of string
  oce_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "oce_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_oce_oce_instance" "this" {
  oce_instance_id = var.oce_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "admin_email" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.admin_email
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_oce_oce_instance.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_oce_oce_instance.this.freeform_tags
}

output "guid" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.guid
}

output "id" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.id
}

output "idcs_access_token" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.idcs_access_token
  sensitive   = true
}

output "idcs_tenancy" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.idcs_tenancy
}

output "instance_access_type" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.instance_access_type
}

output "instance_license_type" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.instance_license_type
}

output "instance_usage_type" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.instance_usage_type
}

output "name" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.name
}

output "object_storage_namespace" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.object_storage_namespace
}

output "service" {
  description = "returns a map of string"
  value       = data.oci_oce_oce_instance.this.service
}

output "state" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.state_message
}

output "tenancy_id" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.tenancy_id
}

output "tenancy_name" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.tenancy_name
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.time_updated
}

output "upgrade_schedule" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.upgrade_schedule
}

output "waf_primary_domain" {
  description = "returns a string"
  value       = data.oci_oce_oce_instance.this.waf_primary_domain
}

output "this" {
  value = oci_oce_oce_instance.this
}
```

[top](#index)