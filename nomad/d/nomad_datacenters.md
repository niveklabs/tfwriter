# nomad_datacenters

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
module "nomad_datacenters" {
  source = "./modules/nomad/d/nomad_datacenters"

  # ignore_down_nodes - (optional) is a type of bool
  ignore_down_nodes = null
  # prefix - (optional) is a type of string
  prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "ignore_down_nodes" {
  description = "(optional) - If enabled, this flag will ignore nodes that are down when listing datacenters."
  type        = bool
  default     = null
}

variable "prefix" {
  description = "(optional) - Prefix value used for filtering results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_datacenters" "this" {
  ignore_down_nodes = var.ignore_down_nodes
  prefix            = var.prefix
}
```

[top](#index)

### Outputs

```terraform
output "datacenters" {
  description = "returns a list of string"
  value       = data.nomad_datacenters.this.datacenters
}

output "id" {
  description = "returns a string"
  value       = data.nomad_datacenters.this.id
}

output "this" {
  value = nomad_datacenters.this
}
```

[top](#index)