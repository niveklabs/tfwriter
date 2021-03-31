# oci_logging_unified_agent_configuration

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_logging_unified_agent_configuration" {
  source = "./modules/oci/d/oci_logging_unified_agent_configuration"

  # unified_agent_configuration_id - (required) is a type of string
  unified_agent_configuration_id = null
}
```

[top](#index)

### Variables

```terraform
variable "unified_agent_configuration_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_logging_unified_agent_configuration" "this" {
  unified_agent_configuration_id = var.unified_agent_configuration_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.compartment_id
}

output "configuration_state" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.configuration_state
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_unified_agent_configuration.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_unified_agent_configuration.this.freeform_tags
}

output "group_association" {
  description = "returns a list of object"
  value       = data.oci_logging_unified_agent_configuration.this.group_association
}

output "id" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_logging_unified_agent_configuration.this.is_enabled
}

output "service_configuration" {
  description = "returns a list of object"
  value       = data.oci_logging_unified_agent_configuration.this.service_configuration
}

output "state" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.time_created
}

output "time_last_modified" {
  description = "returns a string"
  value       = data.oci_logging_unified_agent_configuration.this.time_last_modified
}

output "this" {
  value = oci_logging_unified_agent_configuration.this
}
```

[top](#index)