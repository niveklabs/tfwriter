# oci_vault_secret_version

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
module "oci_vault_secret_version" {
  source = "./modules/oci/d/oci_vault_secret_version"

  # secret_id - (required) is a type of string
  secret_id = null
  # secret_version_number - (required) is a type of string
  secret_version_number = null
}
```

[top](#index)

### Variables

```terraform
variable "secret_id" {
  description = "(required)"
  type        = string
}

variable "secret_version_number" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_vault_secret_version" "this" {
  secret_id             = var.secret_id
  secret_version_number = var.secret_version_number
}
```

[top](#index)

### Outputs

```terraform
output "content_type" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.content_type
}

output "id" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.name
}

output "stages" {
  description = "returns a list of string"
  value       = data.oci_vault_secret_version.this.stages
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.time_created
}

output "time_of_current_version_expiry" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.time_of_current_version_expiry
}

output "time_of_deletion" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.time_of_deletion
}

output "version_number" {
  description = "returns a string"
  value       = data.oci_vault_secret_version.this.version_number
}

output "this" {
  value = oci_vault_secret_version.this
}
```

[top](#index)