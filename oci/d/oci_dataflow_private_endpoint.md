# oci_dataflow_private_endpoint

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
module "oci_dataflow_private_endpoint" {
  source = "./modules/oci/d/oci_dataflow_private_endpoint"

  # private_endpoint_id - (required) is a type of string
  private_endpoint_id = null
}
```

[top](#index)

### Variables

```terraform
variable "private_endpoint_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dataflow_private_endpoint" "this" {
  # private_endpoint_id - (required) is a type of string
  private_endpoint_id = var.private_endpoint_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_dataflow_private_endpoint.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.display_name
}

output "dns_zones" {
  description = "returns a list of string"
  value       = data.oci_dataflow_private_endpoint.this.dns_zones
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_dataflow_private_endpoint.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.lifecycle_details
}

output "max_host_count" {
  description = "returns a number"
  value       = data.oci_dataflow_private_endpoint.this.max_host_count
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_dataflow_private_endpoint.this.nsg_ids
}

output "owner_principal_id" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.owner_principal_id
}

output "owner_user_name" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.owner_user_name
}

output "state" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_dataflow_private_endpoint.this.time_updated
}

output "this" {
  value = oci_dataflow_private_endpoint.this
}
```

[top](#index)