# oci_identity_ui_password

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
module "oci_identity_ui_password" {
  source = "./modules/oci/d/oci_identity_ui_password"

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
data "oci_identity_ui_password" "this" {
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_identity_ui_password.this.id
}

output "inactive_status" {
  description = "returns a string"
  value       = data.oci_identity_ui_password.this.inactive_status
}

output "password" {
  description = "returns a string"
  value       = data.oci_identity_ui_password.this.password
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_ui_password.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_ui_password.this.time_created
}

output "this" {
  value = oci_identity_ui_password.this
}
```

[top](#index)