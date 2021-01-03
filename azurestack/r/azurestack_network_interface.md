# azurestack_network_interface

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
module "azurestack_network_interface" {
  source = "./modules/azurestack/r/azurestack_network_interface"

  # applied_dns_servers - (optional) is a type of set of string
  applied_dns_servers = []
  # dns_servers - (optional) is a type of set of string
  dns_servers = []
  # enable_ip_forwarding - (optional) is a type of bool
  enable_ip_forwarding = null
  # internal_dns_name_label - (optional) is a type of string
  internal_dns_name_label = null
  # internal_fqdn - (optional) is a type of string
  internal_fqdn = null
  # location - (required) is a type of string
  location = null
  # mac_address - (optional) is a type of string
  mac_address = null
  # name - (required) is a type of string
  name = null
  # network_security_group_id - (optional) is a type of string
  network_security_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_machine_id - (optional) is a type of string
  virtual_machine_id = null

  ip_configuration = [{
    application_gateway_backend_address_pools_ids = []
    application_security_group_ids                = []
    load_balancer_backend_address_pools_ids       = []
    load_balancer_inbound_nat_rules_ids           = []
    name                                          = null
    primary                                       = null
    private_ip_address                            = null
    private_ip_address_allocation                 = null
    public_ip_address_id                          = null
    subnet_id                                     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "applied_dns_servers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "dns_servers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "enable_ip_forwarding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "internal_dns_name_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internal_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "mac_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "virtual_machine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      application_gateway_backend_address_pools_ids = set(string)
      application_security_group_ids                = set(string)
      load_balancer_backend_address_pools_ids       = set(string)
      load_balancer_inbound_nat_rules_ids           = set(string)
      name                                          = string
      primary                                       = bool
      private_ip_address                            = string
      private_ip_address_allocation                 = string
      public_ip_address_id                          = string
      subnet_id                                     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_network_interface" "this" {
  applied_dns_servers       = var.applied_dns_servers
  dns_servers               = var.dns_servers
  enable_ip_forwarding      = var.enable_ip_forwarding
  internal_dns_name_label   = var.internal_dns_name_label
  internal_fqdn             = var.internal_fqdn
  location                  = var.location
  mac_address               = var.mac_address
  name                      = var.name
  network_security_group_id = var.network_security_group_id
  resource_group_name       = var.resource_group_name
  tags                      = var.tags
  virtual_machine_id        = var.virtual_machine_id

  dynamic "ip_configuration" {
    for_each = var.ip_configuration
    content {
      application_gateway_backend_address_pools_ids = ip_configuration.value["application_gateway_backend_address_pools_ids"]
      application_security_group_ids                = ip_configuration.value["application_security_group_ids"]
      load_balancer_backend_address_pools_ids       = ip_configuration.value["load_balancer_backend_address_pools_ids"]
      load_balancer_inbound_nat_rules_ids           = ip_configuration.value["load_balancer_inbound_nat_rules_ids"]
      name                                          = ip_configuration.value["name"]
      primary                                       = ip_configuration.value["primary"]
      private_ip_address                            = ip_configuration.value["private_ip_address"]
      private_ip_address_allocation                 = ip_configuration.value["private_ip_address_allocation"]
      public_ip_address_id                          = ip_configuration.value["public_ip_address_id"]
      subnet_id                                     = ip_configuration.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "applied_dns_servers" {
  description = "returns a set of string"
  value       = azurestack_network_interface.this.applied_dns_servers
}

output "dns_servers" {
  description = "returns a set of string"
  value       = azurestack_network_interface.this.dns_servers
}

output "id" {
  description = "returns a string"
  value       = azurestack_network_interface.this.id
}

output "internal_dns_name_label" {
  description = "returns a string"
  value       = azurestack_network_interface.this.internal_dns_name_label
}

output "internal_fqdn" {
  description = "returns a string"
  value       = azurestack_network_interface.this.internal_fqdn
}

output "mac_address" {
  description = "returns a string"
  value       = azurestack_network_interface.this.mac_address
}

output "private_ip_address" {
  description = "returns a string"
  value       = azurestack_network_interface.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurestack_network_interface.this.private_ip_addresses
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_network_interface.this.tags
}

output "virtual_machine_id" {
  description = "returns a string"
  value       = azurestack_network_interface.this.virtual_machine_id
}

output "this" {
  value = azurestack_network_interface.this
}
```

[top](#index)