# oci_kms_vault_usage

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
module "oci_kms_vault_usage" {
  source = "./modules/oci/d/oci_kms_vault_usage"

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
data "oci_kms_vault_usage" "this" {
  vault_id = var.vault_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_kms_vault_usage.this.id
}

output "key_count" {
  description = "returns a number"
  value       = data.oci_kms_vault_usage.this.key_count
}

output "key_version_count" {
  description = "returns a number"
  value       = data.oci_kms_vault_usage.this.key_version_count
}

output "software_key_count" {
  description = "returns a number"
  value       = data.oci_kms_vault_usage.this.software_key_count
}

output "software_key_version_count" {
  description = "returns a number"
  value       = data.oci_kms_vault_usage.this.software_key_version_count
}

output "this" {
  value = oci_kms_vault_usage.this
}
```

[top](#index)