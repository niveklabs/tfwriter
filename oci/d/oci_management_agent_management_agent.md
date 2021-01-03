# oci_management_agent_management_agent

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
module "oci_management_agent_management_agent" {
  source = "./modules/oci/d/oci_management_agent_management_agent"

  # management_agent_id - (required) is a type of string
  management_agent_id = null
}
```

[top](#index)

### Variables

```terraform
variable "management_agent_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_management_agent_management_agent" "this" {
  management_agent_id = var.management_agent_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_status" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.availability_status
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_management_agent_management_agent.this.defined_tags
}

output "deploy_plugins_id" {
  description = "returns a list of string"
  value       = data.oci_management_agent_management_agent.this.deploy_plugins_id
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_management_agent_management_agent.this.freeform_tags
}

output "host" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.host
}

output "id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.id
}

output "install_key_id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.install_key_id
}

output "install_path" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.install_path
}

output "is_agent_auto_upgradable" {
  description = "returns a bool"
  value       = data.oci_management_agent_management_agent.this.is_agent_auto_upgradable
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.lifecycle_details
}

output "managed_agent_id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.managed_agent_id
}

output "platform_name" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.platform_name
}

output "platform_type" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.platform_type
}

output "platform_version" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.platform_version
}

output "plugin_list" {
  description = "returns a list of object"
  value       = data.oci_management_agent_management_agent.this.plugin_list
}

output "state" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.time_created
}

output "time_last_heartbeat" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.time_last_heartbeat
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.time_updated
}

output "version" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent.this.version
}

output "this" {
  value = oci_management_agent_management_agent.this
}
```

[top](#index)