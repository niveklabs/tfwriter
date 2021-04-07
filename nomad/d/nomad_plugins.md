# nomad_plugins

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
module "nomad_plugins" {
  source = "./modules/nomad/d/nomad_plugins"

  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "type" {
  description = "(optional) - Volume Type (currently only 'csi')"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_plugins" "this" {
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_plugins.this.id
}

output "plugins" {
  description = "returns a list of map of string"
  value       = data.nomad_plugins.this.plugins
}

output "this" {
  value = nomad_plugins.this
}
```

[top](#index)