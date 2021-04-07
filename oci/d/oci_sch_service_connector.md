# oci_sch_service_connector

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
module "oci_sch_service_connector" {
  source = "./modules/oci/d/oci_sch_service_connector"

  # service_connector_id - (required) is a type of string
  service_connector_id = null
}
```

[top](#index)

### Variables

```terraform
variable "service_connector_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_sch_service_connector" "this" {
  service_connector_id = var.service_connector_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_sch_service_connector.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_sch_service_connector.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.id
}

output "lifecyle_details" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.lifecyle_details
}

output "source" {
  description = "returns a list of object"
  value       = data.oci_sch_service_connector.this.source
}

output "state" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_sch_service_connector.this.system_tags
}

output "target" {
  description = "returns a list of object"
  value       = data.oci_sch_service_connector.this.target
}

output "tasks" {
  description = "returns a list of object"
  value       = data.oci_sch_service_connector.this.tasks
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_sch_service_connector.this.time_updated
}

output "this" {
  value = oci_sch_service_connector.this
}
```

[top](#index)