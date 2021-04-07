# oci_computeinstanceagent_instance_agent_plugin

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
module "oci_computeinstanceagent_instance_agent_plugin" {
  source = "./modules/oci/d/oci_computeinstanceagent_instance_agent_plugin"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # instanceagent_id - (required) is a type of string
  instanceagent_id = null
  # plugin_name - (required) is a type of string
  plugin_name = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "instanceagent_id" {
  description = "(required)"
  type        = string
}

variable "plugin_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_computeinstanceagent_instance_agent_plugin" "this" {
  compartment_id   = var.compartment_id
  instanceagent_id = var.instanceagent_id
  plugin_name      = var.plugin_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_computeinstanceagent_instance_agent_plugin.this.id
}

output "message" {
  description = "returns a string"
  value       = data.oci_computeinstanceagent_instance_agent_plugin.this.message
}

output "name" {
  description = "returns a string"
  value       = data.oci_computeinstanceagent_instance_agent_plugin.this.name
}

output "status" {
  description = "returns a string"
  value       = data.oci_computeinstanceagent_instance_agent_plugin.this.status
}

output "time_last_updated_utc" {
  description = "returns a string"
  value       = data.oci_computeinstanceagent_instance_agent_plugin.this.time_last_updated_utc
}

output "this" {
  value = oci_computeinstanceagent_instance_agent_plugin.this
}
```

[top](#index)