# oci_core_public_ip_pool

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
module "oci_core_public_ip_pool" {
  source = "./modules/oci/d/oci_core_public_ip_pool"

  # public_ip_pool_id - (required) is a type of string
  public_ip_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "public_ip_pool_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_public_ip_pool" "this" {
  public_ip_pool_id = var.public_ip_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.oci_core_public_ip_pool.this.cidr_blocks
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_core_public_ip_pool.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_core_public_ip_pool.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_core_public_ip_pool.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_core_public_ip_pool.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_public_ip_pool.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_core_public_ip_pool.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_core_public_ip_pool.this.time_created
}

output "this" {
  value = oci_core_public_ip_pool.this
}
```

[top](#index)