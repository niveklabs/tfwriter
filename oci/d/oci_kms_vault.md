# oci_kms_vault

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
module "oci_kms_vault" {
  source = "./modules/oci/d/oci_kms_vault"

  # vault_id - (required) is a type of string
  vault_id = null
}
```

[top](#index)

### Variables

```terraform
variable "vault_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_kms_vault" "this" {
  vault_id = var.vault_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.compartment_id
}

output "crypto_endpoint" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.crypto_endpoint
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_kms_vault.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_kms_vault.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.id
}

output "management_endpoint" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.management_endpoint
}

output "restore_from_file" {
  description = "returns a list of object"
  value       = data.oci_kms_vault.this.restore_from_file
}

output "restore_from_object_store" {
  description = "returns a list of object"
  value       = data.oci_kms_vault.this.restore_from_object_store
}

output "restore_trigger" {
  description = "returns a bool"
  value       = data.oci_kms_vault.this.restore_trigger
}

output "restored_from_vault_id" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.restored_from_vault_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.time_created
}

output "time_of_deletion" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.time_of_deletion
}

output "vault_type" {
  description = "returns a string"
  value       = data.oci_kms_vault.this.vault_type
}

output "this" {
  value = oci_kms_vault.this
}
```

[top](#index)