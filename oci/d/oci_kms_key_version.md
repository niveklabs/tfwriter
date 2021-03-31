# oci_kms_key_version

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
module "oci_kms_key_version" {
  source = "./modules/oci/d/oci_kms_key_version"

  # key_id - (required) is a type of string
  key_id = null
  # key_version_id - (required) is a type of string
  key_version_id = null
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

variable "key_version_id" {
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
data "oci_kms_key_version" "this" {
  key_id              = var.key_id
  key_version_id      = var.key_version_id
  management_endpoint = var.management_endpoint
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.id
}

output "public_key" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.public_key
}

output "restored_from_key_id" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.restored_from_key_id
}

output "restored_from_key_version_id" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.restored_from_key_version_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.time_created
}

output "time_of_deletion" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.time_of_deletion
}

output "vault_id" {
  description = "returns a string"
  value       = data.oci_kms_key_version.this.vault_id
}

output "this" {
  value = oci_kms_key_version.this
}
```

[top](#index)