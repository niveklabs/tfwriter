# oci_identity_availability_domain

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
module "oci_identity_availability_domain" {
  source = "./modules/oci/d/oci_identity_availability_domain"

  # ad_number - (optional) is a type of number
  ad_number = null
  # compartment_id - (required) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ad_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_availability_domain" "this" {
  # ad_number - (optional) is a type of number
  ad_number = var.ad_number
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "ad_number" {
  description = "returns a number"
  value       = data.oci_identity_availability_domain.this.ad_number
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_availability_domain.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_availability_domain.this.name
}

output "this" {
  value = oci_identity_availability_domain.this
}
```

[top](#index)