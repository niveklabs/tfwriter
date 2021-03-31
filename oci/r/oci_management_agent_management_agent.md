# oci_management_agent_management_agent

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_management_agent_management_agent" {
  source = "./modules/oci/r/oci_management_agent_management_agent"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # deploy_plugins_id - (optional) is a type of list of string
  deploy_plugins_id = []
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_agent_auto_upgradable - (optional) is a type of bool
  is_agent_auto_upgradable = null
  # managed_agent_id - (required) is a type of string
  managed_agent_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "deploy_plugins_id" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_agent_auto_upgradable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "managed_agent_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_management_agent_management_agent" "this" {
  defined_tags             = var.defined_tags
  deploy_plugins_id        = var.deploy_plugins_id
  display_name             = var.display_name
  freeform_tags            = var.freeform_tags
  is_agent_auto_upgradable = var.is_agent_auto_upgradable
  managed_agent_id         = var.managed_agent_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_status" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.availability_status
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_management_agent_management_agent.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_management_agent_management_agent.this.freeform_tags
}

output "host" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.host
}

output "id" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.id
}

output "install_key_id" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.install_key_id
}

output "install_path" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.install_path
}

output "is_agent_auto_upgradable" {
  description = "returns a bool"
  value       = oci_management_agent_management_agent.this.is_agent_auto_upgradable
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.lifecycle_details
}

output "platform_name" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.platform_name
}

output "platform_type" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.platform_type
}

output "platform_version" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.platform_version
}

output "plugin_list" {
  description = "returns a list of object"
  value       = oci_management_agent_management_agent.this.plugin_list
}

output "state" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.time_created
}

output "time_last_heartbeat" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.time_last_heartbeat
}

output "time_updated" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.time_updated
}

output "version" {
  description = "returns a string"
  value       = oci_management_agent_management_agent.this.version
}

output "this" {
  value = oci_management_agent_management_agent.this
}
```

[top](#index)