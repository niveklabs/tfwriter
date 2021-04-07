# azurestack_dns_zone

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
module "azurestack_dns_zone" {
  source = "./modules/azurestack/r/azurestack_dns_zone"

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

### Resource

```terraform
resource "azurestack_dns_zone" "this" {
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
output "id" {
  description = "returns a string"
  value       = azurestack_dns_zone.this.id
}

output "max_number_of_record_sets" {
  description = "returns a number"
  value       = azurestack_dns_zone.this.max_number_of_record_sets
}

output "name_servers" {
  description = "returns a set of string"
  value       = azurestack_dns_zone.this.name_servers
}

output "number_of_record_sets" {
  description = "returns a number"
  value       = azurestack_dns_zone.this.number_of_record_sets
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_dns_zone.this.tags
}

output "this" {
  value = azurestack_dns_zone.this
}
```

[top](#index)