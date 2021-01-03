# azurestack_public_ip

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
module "azurestack_public_ip" {
  source = "./modules/azurestack/r/azurestack_public_ip"

  # domain_name_label - (optional) is a type of string
  domain_name_label = null
  # idle_timeout_in_minutes - (optional) is a type of number
  idle_timeout_in_minutes = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # public_ip_address_allocation - (required) is a type of string
  public_ip_address_allocation = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # reverse_fqdn - (optional) is a type of string
  reverse_fqdn = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "domain_name_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idle_timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_ip_address_allocation" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "reverse_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurestack_public_ip" "this" {
  domain_name_label            = var.domain_name_label
  idle_timeout_in_minutes      = var.idle_timeout_in_minutes
  location                     = var.location
  name                         = var.name
  public_ip_address_allocation = var.public_ip_address_allocation
  resource_group_name          = var.resource_group_name
  reverse_fqdn                 = var.reverse_fqdn
  tags                         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "fqdn" {
  description = "returns a string"
  value       = azurestack_public_ip.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurestack_public_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = azurestack_public_ip.this.ip_address
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_public_ip.this.tags
}

output "this" {
  value = azurestack_public_ip.this
}
```

[top](#index)