# oci_limits_resource_availability

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
module "oci_limits_resource_availability" {
  source = "./modules/oci/d/oci_limits_resource_availability"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # limit_name - (required) is a type of string
  limit_name = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "limit_name" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_limits_resource_availability" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  limit_name          = var.limit_name
  service_name        = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "available" {
  description = "returns a string"
  value       = data.oci_limits_resource_availability.this.available
}

output "id" {
  description = "returns a string"
  value       = data.oci_limits_resource_availability.this.id
}

output "used" {
  description = "returns a string"
  value       = data.oci_limits_resource_availability.this.used
}

output "this" {
  value = oci_limits_resource_availability.this
}
```

[top](#index)