# oci_data_safe_on_prem_connector

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
module "oci_data_safe_on_prem_connector" {
  source = "./modules/oci/d/oci_data_safe_on_prem_connector"

  # on_prem_connector_id - (required) is a type of string
  on_prem_connector_id = null
}
```

[top](#index)

### Variables

```terraform
variable "on_prem_connector_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_data_safe_on_prem_connector" "this" {
  on_prem_connector_id = var.on_prem_connector_id
}
```

[top](#index)

### Outputs

```terraform
output "available_version" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.available_version
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.compartment_id
}

output "created_version" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.created_version
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_data_safe_on_prem_connector.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_data_safe_on_prem_connector.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_data_safe_on_prem_connector.this.time_created
}

output "this" {
  value = oci_data_safe_on_prem_connector.this
}
```

[top](#index)