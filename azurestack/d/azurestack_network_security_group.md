# azurestack_network_security_group

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurestack_network_security_group" {
  source = "./modules/azurestack/d/azurestack_network_security_group"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_network_security_group" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurestack_network_security_group.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurestack_network_security_group.this.location
}

output "security_rule" {
  description = "returns a list of object"
  value       = data.azurestack_network_security_group.this.security_rule
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_network_security_group.this.tags
}

output "this" {
  value = azurestack_network_security_group.this
}
```

[top](#index)