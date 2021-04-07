# consul_intention

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
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_intention" {
  source = "./modules/consul/r/consul_intention"

  # action - (required) is a type of string
  action = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # description - (optional) is a type of string
  description = null
  # destination_name - (required) is a type of string
  destination_name = null
  # destination_namespace - (optional) is a type of string
  destination_namespace = null
  # meta - (optional) is a type of map of string
  meta = {}
  # source_name - (required) is a type of string
  source_name = null
  # source_namespace - (optional) is a type of string
  source_namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_name" {
  description = "(required)"
  type        = string
}

variable "destination_namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "source_name" {
  description = "(required)"
  type        = string
}

variable "source_namespace" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_intention" "this" {
  # action - (required) is a type of string
  action = var.action
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # description - (optional) is a type of string
  description = var.description
  # destination_name - (required) is a type of string
  destination_name = var.destination_name
  # destination_namespace - (optional) is a type of string
  destination_namespace = var.destination_namespace
  # meta - (optional) is a type of map of string
  meta = var.meta
  # source_name - (required) is a type of string
  source_name = var.source_name
  # source_namespace - (optional) is a type of string
  source_namespace = var.source_namespace
}
```

[top](#index)

### Outputs

```terraform
output "datacenter" {
  description = "returns a string"
  value       = consul_intention.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_intention.this.id
}

output "this" {
  value = consul_intention.this
}
```

[top](#index)