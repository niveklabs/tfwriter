# oci_kms_key

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_kms_key" {
  source = "./modules/oci/d/oci_kms_key"

  # key_id - (required) is a type of string
  key_id = null
  # management_endpoint - (required) is a type of string
  management_endpoint = null
}
```

[top](#index)

### Variables

```terraform
variable "key_id" {
  description = "(required)"
  type        = string
}

variable "management_endpoint" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_kms_key" "this" {
  key_id              = var.key_id
  management_endpoint = var.management_endpoint
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_kms_key.this.compartment_id
}

output "current_key_version" {
  description = "returns a string"
  value       = data.oci_kms_key.this.current_key_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_kms_key.this.defined_tags
}

output "desired_state" {
  description = "returns a string"
  value       = data.oci_kms_key.this.desired_state
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_kms_key.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_kms_key.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_kms_key.this.id
}

output "key_shape" {
  description = "returns a list of object"
  value       = data.oci_kms_key.this.key_shape
}

output "protection_mode" {
  description = "returns a string"
  value       = data.oci_kms_key.this.protection_mode
}

output "restore_from_file" {
  description = "returns a list of object"
  value       = data.oci_kms_key.this.restore_from_file
}

output "restore_from_object_store" {
  description = "returns a list of object"
  value       = data.oci_kms_key.this.restore_from_object_store
}

output "restore_trigger" {
  description = "returns a bool"
  value       = data.oci_kms_key.this.restore_trigger
}

output "restored_from_key_id" {
  description = "returns a string"
  value       = data.oci_kms_key.this.restored_from_key_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_kms_key.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_kms_key.this.time_created
}

output "time_of_deletion" {
  description = "returns a string"
  value       = data.oci_kms_key.this.time_of_deletion
}

output "vault_id" {
  description = "returns a string"
  value       = data.oci_kms_key.this.vault_id
}

output "this" {
  value = oci_kms_key.this
}
```

[top](#index)