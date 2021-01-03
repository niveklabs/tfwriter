# oci_data_safe_data_safe_private_endpoint

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
module "oci_data_safe_data_safe_private_endpoint" {
  source = "./modules/oci/d/oci_data_safe_data_safe_private_endpoint"

  # data_safe_private_endpoint_id - (required) is a type of string
  data_safe_private_endpoint_id = null
}
```

[top](#index)

### Variables

```terraform
variable "data_safe_private_endpoint_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_data_safe_data_safe_private_endpoint" "this" {
  data_safe_private_endpoint_id = var.data_safe_private_endpoint_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.display_name
}

output "endpoint_fqdn" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.endpoint_fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.id
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.nsg_ids
}

output "private_endpoint_id" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.private_endpoint_id
}

output "private_endpoint_ip" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.private_endpoint_ip
}

output "state" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.time_created
}

output "vcn_id" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_private_endpoint.this.vcn_id
}

output "this" {
  value = oci_data_safe_data_safe_private_endpoint.this
}
```

[top](#index)