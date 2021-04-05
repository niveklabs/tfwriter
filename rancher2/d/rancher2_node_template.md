# rancher2_node_template

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_node_template" {
  source = "./modules/rancher2/d/rancher2_node_template"

  # name - (required) is a type of string
  name = null
  # use_internal_ip_address - (optional) is a type of bool
  use_internal_ip_address = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "use_internal_ip_address" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_node_template" "this" {
  name                    = var.name
  use_internal_ip_address = var.use_internal_ip_address
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_node_template.this.annotations
}

output "cloud_credential_id" {
  description = "returns a string"
  value       = data.rancher2_node_template.this.cloud_credential_id
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_node_template.this.description
}

output "driver" {
  description = "returns a string"
  value       = data.rancher2_node_template.this.driver
}

output "engine_env" {
  description = "returns a map of string"
  value       = data.rancher2_node_template.this.engine_env
}

output "engine_insecure_registry" {
  description = "returns a list of string"
  value       = data.rancher2_node_template.this.engine_insecure_registry
}

output "engine_install_url" {
  description = "returns a string"
  value       = data.rancher2_node_template.this.engine_install_url
}

output "engine_label" {
  description = "returns a map of string"
  value       = data.rancher2_node_template.this.engine_label
}

output "engine_opt" {
  description = "returns a map of string"
  value       = data.rancher2_node_template.this.engine_opt
}

output "engine_registry_mirror" {
  description = "returns a list of string"
  value       = data.rancher2_node_template.this.engine_registry_mirror
}

output "engine_storage_driver" {
  description = "returns a string"
  value       = data.rancher2_node_template.this.engine_storage_driver
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_node_template.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_node_template.this.labels
}

output "node_taints" {
  description = "returns a list of object"
  value       = data.rancher2_node_template.this.node_taints
}

output "this" {
  value = rancher2_node_template.this
}
```

[top](#index)