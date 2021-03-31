# nomad_plugin

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.13"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_plugin" {
  source = "./modules/nomad/d/nomad_plugin"

  # plugin_id - (required) is a type of string
  plugin_id = null
  # wait_for_healthy - (optional) is a type of bool
  wait_for_healthy = null
  # wait_for_registration - (optional) is a type of bool
  wait_for_registration = null
}
```

[top](#index)

### Variables

```terraform
variable "plugin_id" {
  description = "(required) - Plugin ID"
  type        = string
}

variable "wait_for_healthy" {
  description = "(optional) - Wait for to be backed by a specified number of controllers"
  type        = bool
  default     = null
}

variable "wait_for_registration" {
  description = "(optional) - Wait for the plugin to be registered in Noamd"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_plugin" "this" {
  plugin_id             = var.plugin_id
  wait_for_healthy      = var.wait_for_healthy
  wait_for_registration = var.wait_for_registration
}
```

[top](#index)

### Outputs

```terraform
output "controller_required" {
  description = "returns a bool"
  value       = data.nomad_plugin.this.controller_required
}

output "controllers_expected" {
  description = "returns a number"
  value       = data.nomad_plugin.this.controllers_expected
}

output "controllers_healthy" {
  description = "returns a number"
  value       = data.nomad_plugin.this.controllers_healthy
}

output "id" {
  description = "returns a string"
  value       = data.nomad_plugin.this.id
}

output "nodes" {
  description = "returns a list of object"
  value       = data.nomad_plugin.this.nodes
}

output "nodes_expected" {
  description = "returns a number"
  value       = data.nomad_plugin.this.nodes_expected
}

output "nodes_healthy" {
  description = "returns a number"
  value       = data.nomad_plugin.this.nodes_healthy
}

output "plugin_provider" {
  description = "returns a string"
  value       = data.nomad_plugin.this.plugin_provider
}

output "plugin_provider_version" {
  description = "returns a string"
  value       = data.nomad_plugin.this.plugin_provider_version
}

output "this" {
  value = nomad_plugin.this
}
```

[top](#index)