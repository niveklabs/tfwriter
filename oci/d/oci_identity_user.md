# oci_identity_user

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
module "oci_identity_user" {
  source = "./modules/oci/d/oci_identity_user"

  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "user_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_user" "this" {
  # user_id - (required) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "capabilities" {
  description = "returns a list of object"
  value       = data.oci_identity_user.this.capabilities
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_identity_user.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_user.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_identity_user.this.description
}

output "email" {
  description = "returns a string"
  value       = data.oci_identity_user.this.email
}

output "email_verified" {
  description = "returns a bool"
  value       = data.oci_identity_user.this.email_verified
}

output "external_identifier" {
  description = "returns a string"
  value       = data.oci_identity_user.this.external_identifier
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_user.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_user.this.id
}

output "identity_provider_id" {
  description = "returns a string"
  value       = data.oci_identity_user.this.identity_provider_id
}

output "inactive_state" {
  description = "returns a string"
  value       = data.oci_identity_user.this.inactive_state
}

output "last_successful_login_time" {
  description = "returns a string"
  value       = data.oci_identity_user.this.last_successful_login_time
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_user.this.name
}

output "previous_successful_login_time" {
  description = "returns a string"
  value       = data.oci_identity_user.this.previous_successful_login_time
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_user.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_user.this.time_created
}

output "this" {
  value = oci_identity_user.this
}
```

[top](#index)