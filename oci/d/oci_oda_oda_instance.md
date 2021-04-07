# oci_oda_oda_instance

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
module "oci_oda_oda_instance" {
  source = "./modules/oci/d/oci_oda_oda_instance"

  # oda_instance_id - (required) is a type of string
  oda_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "oda_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_oda_oda_instance" "this" {
  # oda_instance_id - (required) is a type of string
  oda_instance_id = var.oda_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.compartment_id
}

output "connector_url" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.connector_url
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_oda_oda_instance.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_oda_oda_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.id
}

output "lifecycle_sub_state" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.lifecycle_sub_state
}

output "shape_name" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.shape_name
}

output "state" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.state_message
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.time_updated
}

output "web_app_url" {
  description = "returns a string"
  value       = data.oci_oda_oda_instance.this.web_app_url
}

output "this" {
  value = oci_oda_oda_instance.this
}
```

[top](#index)