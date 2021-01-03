# consul_config_entry

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.10.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_config_entry" {
  source = "./modules/consul/r/consul_config_entry"

  # config_json - (optional) is a type of string
  config_json = null
  # kind - (required) is a type of string
  kind = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "config_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kind" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "consul_config_entry" "this" {
  config_json = var.config_json
  kind        = var.kind
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_config_entry.this.id
}

output "this" {
  value = consul_config_entry.this
}
```

[top](#index)