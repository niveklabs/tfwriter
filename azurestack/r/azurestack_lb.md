# azurestack_lb

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
module "azurestack_lb" {
  source = "./modules/azurestack/r/azurestack_lb"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  frontend_ip_configuration = [{
    inbound_nat_rules             = []
    load_balancer_rules           = []
    name                          = null
    private_ip_address            = null
    private_ip_address_allocation = null
    public_ip_address_id          = null
    subnet_id                     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required)"
  type        = string
}

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

variable "frontend_ip_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      inbound_nat_rules             = set(string)
      load_balancer_rules           = set(string)
      name                          = string
      private_ip_address            = string
      private_ip_address_allocation = string
      public_ip_address_id          = string
      subnet_id                     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_lb" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "frontend_ip_configuration" {
    for_each = var.frontend_ip_configuration
    content {
      name                          = frontend_ip_configuration.value["name"]
      private_ip_address            = frontend_ip_configuration.value["private_ip_address"]
      private_ip_address_allocation = frontend_ip_configuration.value["private_ip_address_allocation"]
      public_ip_address_id          = frontend_ip_configuration.value["public_ip_address_id"]
      subnet_id                     = frontend_ip_configuration.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_lb.this.id
}

output "private_ip_address" {
  description = "returns a string"
  value       = azurestack_lb.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurestack_lb.this.private_ip_addresses
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_lb.this.tags
}

output "this" {
  value = azurestack_lb.this
}
```

[top](#index)