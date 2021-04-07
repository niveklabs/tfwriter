# oci_identity_authentication_policy

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
module "oci_identity_authentication_policy" {
  source = "./modules/oci/d/oci_identity_authentication_policy"

  # compartment_id - (required) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_authentication_policy" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_identity_authentication_policy.this.id
}

output "network_policy" {
  description = "returns a list of object"
  value       = data.oci_identity_authentication_policy.this.network_policy
}

output "password_policy" {
  description = "returns a list of object"
  value       = data.oci_identity_authentication_policy.this.password_policy
}

output "this" {
  value = oci_identity_authentication_policy.this
}
```

[top](#index)