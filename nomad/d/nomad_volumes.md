# nomad_volumes

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
    nomad = ">= 1.4.14"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_volumes" {
  source = "./modules/nomad/d/nomad_volumes"

  # namespace - (optional) is a type of string
  namespace = null
  # node_id - (optional) is a type of string
  node_id = null
  # plugin_id - (optional) is a type of string
  plugin_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "namespace" {
  description = "(optional) - Volume namespace filter"
  type        = string
  default     = null
}

variable "node_id" {
  description = "(optional) - Volume node filter"
  type        = string
  default     = null
}

variable "plugin_id" {
  description = "(optional) - Plugin ID filter"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Volume Type (currently only 'csi')"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_volumes" "this" {
  namespace = var.namespace
  node_id   = var.node_id
  plugin_id = var.plugin_id
  type      = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_volumes.this.id
}

output "volumes" {
  description = "returns a list of map of string"
  value       = data.nomad_volumes.this.volumes
}

output "this" {
  value = nomad_volumes.this
}
```

[top](#index)