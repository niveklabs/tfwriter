# nutanix_subnet

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/nutanix/d/nutanix_subnet"

  # subnet_id - (optional) is a type of string
  subnet_id = null
  # subnet_name - (optional) is a type of string
  subnet_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_name" {
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

### Datasource

```terraform
data "nutanix_subnet" "this" {
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # subnet_name - (optional) is a type of string
  subnet_name = var.subnet_name

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
  value       = data.nutanix_subnet.this.api_version
}

output "availability_zone_reference" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.availability_zone_reference
}

output "cluster_name" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.cluster_name
}

output "cluster_uuid" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.cluster_uuid
}

output "default_gateway_ip" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.default_gateway_ip
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.description
}

output "dhcp_domain_name_server_list" {
  description = "returns a list of string"
  value       = data.nutanix_subnet.this.dhcp_domain_name_server_list
}

output "dhcp_domain_search_list" {
  description = "returns a list of string"
  value       = data.nutanix_subnet.this.dhcp_domain_search_list
}

output "dhcp_options" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.dhcp_options
}

output "dhcp_server_address" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.dhcp_server_address
}

output "dhcp_server_address_port" {
  description = "returns a number"
  value       = data.nutanix_subnet.this.dhcp_server_address_port
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.id
}

output "ip_config_pool_list_ranges" {
  description = "returns a list of string"
  value       = data.nutanix_subnet.this.ip_config_pool_list_ranges
}

output "message_list" {
  description = "returns a list of object"
  value       = data.nutanix_subnet.this.message_list
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.name
}

output "network_function_chain_reference" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.network_function_chain_reference
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.owner_reference
}

output "prefix_length" {
  description = "returns a number"
  value       = data.nutanix_subnet.this.prefix_length
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_subnet.this.project_reference
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.state
}

output "subnet_ip" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.subnet_ip
}

output "subnet_type" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.subnet_type
}

output "vlan_id" {
  description = "returns a number"
  value       = data.nutanix_subnet.this.vlan_id
}

output "vswitch_name" {
  description = "returns a string"
  value       = data.nutanix_subnet.this.vswitch_name
}

output "this" {
  value = nutanix_subnet.this
}
```

[top](#index)