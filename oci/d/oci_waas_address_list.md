# oci_waas_address_list

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
module "oci_waas_address_list" {
  source = "./modules/oci/d/oci_waas_address_list"

  # address_list_id - (required) is a type of string
  address_list_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address_list_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_address_list" "this" {
  # address_list_id - (required) is a type of string
  address_list_id = var.address_list_id
}
```

[top](#index)

### Outputs

```terraform
output "address_count" {
  description = "returns a number"
  value       = data.oci_waas_address_list.this.address_count
}

output "addresses" {
  description = "returns a list of string"
  value       = data.oci_waas_address_list.this.addresses
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_waas_address_list.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_address_list.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_waas_address_list.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_address_list.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_address_list.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_waas_address_list.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_waas_address_list.this.time_created
}

output "this" {
  value = oci_waas_address_list.this
}
```

[top](#index)