# azurestack_network_security_rule

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_network_security_rule" {
  source = "./modules/azurestack/r/azurestack_network_security_rule"

  # access - (required) is a type of string
  access = null
  # description - (optional) is a type of string
  description = null
  # destination_address_prefix - (optional) is a type of string
  destination_address_prefix = null
  # destination_port_range - (optional) is a type of string
  destination_port_range = null
  # direction - (required) is a type of string
  direction = null
  # name - (required) is a type of string
  name = null
  # network_security_group_name - (required) is a type of string
  network_security_group_name = null
  # priority - (required) is a type of number
  priority = null
  # protocol - (required) is a type of string
  protocol = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_address_prefix - (optional) is a type of string
  source_address_prefix = null
  # source_application_security_group_ids - (optional) is a type of set of string
  source_application_security_group_ids = []
  # source_port_range - (optional) is a type of string
  source_port_range = null
}
```

[top](#index)

### Variables

```terraform
variable "access" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_address_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_port_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "direction" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_security_group_name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_address_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_application_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_port_range" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_network_security_rule" "this" {
  access                                = var.access
  description                           = var.description
  destination_address_prefix            = var.destination_address_prefix
  destination_port_range                = var.destination_port_range
  direction                             = var.direction
  name                                  = var.name
  network_security_group_name           = var.network_security_group_name
  priority                              = var.priority
  protocol                              = var.protocol
  resource_group_name                   = var.resource_group_name
  source_address_prefix                 = var.source_address_prefix
  source_application_security_group_ids = var.source_application_security_group_ids
  source_port_range                     = var.source_port_range
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_network_security_rule.this.id
}

output "this" {
  value = azurestack_network_security_rule.this
}
```

[top](#index)