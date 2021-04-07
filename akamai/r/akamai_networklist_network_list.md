# akamai_networklist_network_list

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_networklist_network_list" {
  source = "./modules/akamai/r/akamai_networklist_network_list"

  # description - (required) is a type of string
  description = null
  # list - (optional) is a type of list of string
  list = []
  # mode - (required) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "mode" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_networklist_network_list" "this" {
  # description - (required) is a type of string
  description = var.description
  # list - (optional) is a type of list of string
  list = var.list
  # mode - (required) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_networklist_network_list.this.id
}

output "sync_point" {
  description = "returns a number"
  value       = akamai_networklist_network_list.this.sync_point
}

output "uniqueid" {
  description = "returns a string"
  value       = akamai_networklist_network_list.this.uniqueid
}

output "this" {
  value = akamai_networklist_network_list.this
}
```

[top](#index)