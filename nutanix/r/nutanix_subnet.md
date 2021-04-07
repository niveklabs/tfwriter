# nutanix_subnet

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_subnet" {
  source = "./modules/nutanix/r/nutanix_subnet"

  # availability_zone_reference - (optional) is a type of map of string
  availability_zone_reference = {}
  # cluster_uuid - (required) is a type of string
  cluster_uuid = null
  # default_gateway_ip - (optional) is a type of string
  default_gateway_ip = null
  # description - (optional) is a type of string
  description = null
  # dhcp_domain_name_server_list - (optional) is a type of list of string
  dhcp_domain_name_server_list = []
  # dhcp_domain_search_list - (optional) is a type of list of string
  dhcp_domain_search_list = []
  # dhcp_options - (optional) is a type of map of string
  dhcp_options = {}
  # dhcp_server_address - (optional) is a type of map of string
  dhcp_server_address = {}
  # dhcp_server_address_port - (optional) is a type of number
  dhcp_server_address_port = null
  # ip_config_pool_list_ranges - (optional) is a type of list of string
  ip_config_pool_list_ranges = []
  # name - (required) is a type of string
  name = null
  # network_function_chain_reference - (optional) is a type of map of string
  network_function_chain_reference = {}
  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # prefix_length - (optional) is a type of number
  prefix_length = null
  # project_reference - (optional) is a type of map of string
  project_reference = {}
  # subnet_ip - (optional) is a type of string
  subnet_ip = null
  # subnet_type - (required) is a type of string
  subnet_type = null
  # vlan_id - (optional) is a type of number
  vlan_id = null
  # vswitch_name - (optional) is a type of string
  vswitch_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cluster_uuid" {
  description = "(required)"
  type        = string
}

variable "default_gateway_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_domain_name_server_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dhcp_domain_search_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dhcp_options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "dhcp_server_address" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "dhcp_server_address_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_config_pool_list_ranges" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_function_chain_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "owner_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "prefix_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "project_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "subnet_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_type" {
  description = "(required)"
  type        = string
}

variable "vlan_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vswitch_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_subnet" "this" {
  # availability_zone_reference - (optional) is a type of map of string
  availability_zone_reference = var.availability_zone_reference
  # cluster_uuid - (required) is a type of string
  cluster_uuid = var.cluster_uuid
  # default_gateway_ip - (optional) is a type of string
  default_gateway_ip = var.default_gateway_ip
  # description - (optional) is a type of string
  description = var.description
  # dhcp_domain_name_server_list - (optional) is a type of list of string
  dhcp_domain_name_server_list = var.dhcp_domain_name_server_list
  # dhcp_domain_search_list - (optional) is a type of list of string
  dhcp_domain_search_list = var.dhcp_domain_search_list
  # dhcp_options - (optional) is a type of map of string
  dhcp_options = var.dhcp_options
  # dhcp_server_address - (optional) is a type of map of string
  dhcp_server_address = var.dhcp_server_address
  # dhcp_server_address_port - (optional) is a type of number
  dhcp_server_address_port = var.dhcp_server_address_port
  # ip_config_pool_list_ranges - (optional) is a type of list of string
  ip_config_pool_list_ranges = var.ip_config_pool_list_ranges
  # name - (required) is a type of string
  name = var.name
  # network_function_chain_reference - (optional) is a type of map of string
  network_function_chain_reference = var.network_function_chain_reference
  # owner_reference - (optional) is a type of map of string
  owner_reference = var.owner_reference
  # prefix_length - (optional) is a type of number
  prefix_length = var.prefix_length
  # project_reference - (optional) is a type of map of string
  project_reference = var.project_reference
  # subnet_ip - (optional) is a type of string
  subnet_ip = var.subnet_ip
  # subnet_type - (required) is a type of string
  subnet_type = var.subnet_type
  # vlan_id - (optional) is a type of number
  vlan_id = var.vlan_id
  # vswitch_name - (optional) is a type of string
  vswitch_name = var.vswitch_name

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_subnet.this.api_version
}

output "availability_zone_reference" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.availability_zone_reference
}

output "cluster_name" {
  description = "returns a string"
  value       = nutanix_subnet.this.cluster_name
}

output "default_gateway_ip" {
  description = "returns a string"
  value       = nutanix_subnet.this.default_gateway_ip
}

output "description" {
  description = "returns a string"
  value       = nutanix_subnet.this.description
}

output "dhcp_domain_name_server_list" {
  description = "returns a list of string"
  value       = nutanix_subnet.this.dhcp_domain_name_server_list
}

output "dhcp_domain_search_list" {
  description = "returns a list of string"
  value       = nutanix_subnet.this.dhcp_domain_search_list
}

output "dhcp_options" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.dhcp_options
}

output "dhcp_server_address" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.dhcp_server_address
}

output "dhcp_server_address_port" {
  description = "returns a number"
  value       = nutanix_subnet.this.dhcp_server_address_port
}

output "id" {
  description = "returns a string"
  value       = nutanix_subnet.this.id
}

output "ip_config_pool_list_ranges" {
  description = "returns a list of string"
  value       = nutanix_subnet.this.ip_config_pool_list_ranges
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.metadata
}

output "network_function_chain_reference" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.network_function_chain_reference
}

output "owner_reference" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.owner_reference
}

output "prefix_length" {
  description = "returns a number"
  value       = nutanix_subnet.this.prefix_length
}

output "project_reference" {
  description = "returns a map of string"
  value       = nutanix_subnet.this.project_reference
}

output "state" {
  description = "returns a string"
  value       = nutanix_subnet.this.state
}

output "subnet_ip" {
  description = "returns a string"
  value       = nutanix_subnet.this.subnet_ip
}

output "vlan_id" {
  description = "returns a number"
  value       = nutanix_subnet.this.vlan_id
}

output "vswitch_name" {
  description = "returns a string"
  value       = nutanix_subnet.this.vswitch_name
}

output "this" {
  value = nutanix_subnet.this
}
```

[top](#index)