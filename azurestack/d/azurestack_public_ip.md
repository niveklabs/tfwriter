# azurestack_public_ip

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
module "azurestack_public_ip" {
  source = "./modules/azurestack/d/azurestack_public_ip"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_public_ip" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "domain_name_label" {
  description = "returns a string"
  value       = data.azurestack_public_ip.this.domain_name_label
}

output "fqdn" {
  description = "returns a string"
  value       = data.azurestack_public_ip.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_public_ip.this.id
}

output "idle_timeout_in_minutes" {
  description = "returns a number"
  value       = data.azurestack_public_ip.this.idle_timeout_in_minutes
}

output "ip_address" {
  description = "returns a string"
  value       = data.azurestack_public_ip.this.ip_address
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_public_ip.this.tags
}

output "this" {
  value = azurestack_public_ip.this
}
```

[top](#index)