# nutanix_network_security_rule

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
module "nutanix_network_security_rule" {
  source = "./modules/nutanix/r/nutanix_network_security_rule"

  # ad_rule_action - (optional) is a type of string
  ad_rule_action = null
  # ad_rule_target_group_default_internal_policy - (optional) is a type of string
  ad_rule_target_group_default_internal_policy = null
  # ad_rule_target_group_filter_kind_list - (optional) is a type of list of string
  ad_rule_target_group_filter_kind_list = []
  # ad_rule_target_group_filter_type - (optional) is a type of string
  ad_rule_target_group_filter_type = null
  # ad_rule_target_group_peer_specification_type - (optional) is a type of string
  ad_rule_target_group_peer_specification_type = null
  # allow_ipv6_traffic - (optional) is a type of bool
  allow_ipv6_traffic = null
  # app_rule_action - (optional) is a type of string
  app_rule_action = null
  # app_rule_target_group_default_internal_policy - (optional) is a type of string
  app_rule_target_group_default_internal_policy = null
  # app_rule_target_group_filter_kind_list - (optional) is a type of list of string
  app_rule_target_group_filter_kind_list = []
  # app_rule_target_group_filter_type - (optional) is a type of string
  app_rule_target_group_filter_type = null
  # app_rule_target_group_peer_specification_type - (optional) is a type of string
  app_rule_target_group_peer_specification_type = null
  # description - (optional) is a type of string
  description = null
  # is_policy_hitlog_enabled - (optional) is a type of bool
  is_policy_hitlog_enabled = null
  # isolation_rule_action - (optional) is a type of string
  isolation_rule_action = null
  # isolation_rule_first_entity_filter_kind_list - (optional) is a type of list of string
  isolation_rule_first_entity_filter_kind_list = []
  # isolation_rule_first_entity_filter_type - (optional) is a type of string
  isolation_rule_first_entity_filter_type = null
  # isolation_rule_second_entity_filter_kind_list - (optional) is a type of list of string
  isolation_rule_second_entity_filter_kind_list = []
  # isolation_rule_second_entity_filter_type - (optional) is a type of string
  isolation_rule_second_entity_filter_type = null
  # name - (required) is a type of string
  name = null
  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # project_reference - (optional) is a type of map of string
  project_reference = {}

  ad_rule_inbound_allow_list = [{
    expiration_time  = null
    filter_kind_list = []
    filter_params = [{
      name   = null
      values = []
    }]
    filter_type = null
    icmp_type_code_list = [{
      code = null
      type = null
    }]
    ip_subnet                        = null
    ip_subnet_prefix_length          = null
    network_function_chain_reference = {}
    peer_specification_type          = null
    protocol                         = null
    tcp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
    udp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
  }]

  ad_rule_outbound_allow_list = [{
    expiration_time  = null
    filter_kind_list = []
    filter_params = [{
      name   = null
      values = []
    }]
    filter_type = null
    icmp_type_code_list = [{
      code = null
      type = null
    }]
    ip_subnet                        = null
    ip_subnet_prefix_length          = null
    network_function_chain_reference = {}
    peer_specification_type          = null
    protocol                         = null
    tcp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
    udp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
  }]

  ad_rule_target_group_filter_params = [{
    name   = null
    values = []
  }]

  app_rule_inbound_allow_list = [{
    expiration_time  = null
    filter_kind_list = []
    filter_params = [{
      name   = null
      values = []
    }]
    filter_type = null
    icmp_type_code_list = [{
      code = null
      type = null
    }]
    ip_subnet                        = null
    ip_subnet_prefix_length          = null
    network_function_chain_reference = {}
    peer_specification_type          = null
    protocol                         = null
    tcp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
    udp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
  }]

  app_rule_outbound_allow_list = [{
    expiration_time  = null
    filter_kind_list = []
    filter_params = [{
      name   = null
      values = []
    }]
    filter_type = null
    icmp_type_code_list = [{
      code = null
      type = null
    }]
    ip_subnet                        = null
    ip_subnet_prefix_length          = null
    network_function_chain_reference = {}
    peer_specification_type          = null
    protocol                         = null
    tcp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
    udp_port_range_list = [{
      end_port   = null
      start_port = null
    }]
  }]

  app_rule_target_group_filter_params = [{
    name   = null
    values = []
  }]

  categories = [{
    name  = null
    value = null
  }]

  isolation_rule_first_entity_filter_params = [{
    name   = null
    values = []
  }]

  isolation_rule_second_entity_filter_params = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ad_rule_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ad_rule_target_group_default_internal_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ad_rule_target_group_filter_kind_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ad_rule_target_group_filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ad_rule_target_group_peer_specification_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_ipv6_traffic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "app_rule_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_rule_target_group_default_internal_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_rule_target_group_filter_kind_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "app_rule_target_group_filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_rule_target_group_peer_specification_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_policy_hitlog_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "isolation_rule_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolation_rule_first_entity_filter_kind_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "isolation_rule_first_entity_filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolation_rule_second_entity_filter_kind_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "isolation_rule_second_entity_filter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ad_rule_inbound_allow_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      expiration_time  = string
      filter_kind_list = list(string)
      filter_params = set(object(
        {
          name   = string
          values = list(string)
        }
      ))
      filter_type = string
      icmp_type_code_list = list(object(
        {
          code = string
          type = string
        }
      ))
      ip_subnet                        = string
      ip_subnet_prefix_length          = string
      network_function_chain_reference = map(string)
      peer_specification_type          = string
      protocol                         = string
      tcp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
      udp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
    }
  ))
  default = []
}

variable "ad_rule_outbound_allow_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      expiration_time  = string
      filter_kind_list = list(string)
      filter_params = set(object(
        {
          name   = string
          values = list(string)
        }
      ))
      filter_type = string
      icmp_type_code_list = list(object(
        {
          code = string
          type = string
        }
      ))
      ip_subnet                        = string
      ip_subnet_prefix_length          = string
      network_function_chain_reference = map(string)
      peer_specification_type          = string
      protocol                         = string
      tcp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
      udp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
    }
  ))
  default = []
}

variable "ad_rule_target_group_filter_params" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}

variable "app_rule_inbound_allow_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      expiration_time  = string
      filter_kind_list = list(string)
      filter_params = set(object(
        {
          name   = string
          values = list(string)
        }
      ))
      filter_type = string
      icmp_type_code_list = list(object(
        {
          code = string
          type = string
        }
      ))
      ip_subnet                        = string
      ip_subnet_prefix_length          = string
      network_function_chain_reference = map(string)
      peer_specification_type          = string
      protocol                         = string
      tcp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
      udp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
    }
  ))
  default = []
}

variable "app_rule_outbound_allow_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      expiration_time  = string
      filter_kind_list = list(string)
      filter_params = set(object(
        {
          name   = string
          values = list(string)
        }
      ))
      filter_type = string
      icmp_type_code_list = list(object(
        {
          code = string
          type = string
        }
      ))
      ip_subnet                        = string
      ip_subnet_prefix_length          = string
      network_function_chain_reference = map(string)
      peer_specification_type          = string
      protocol                         = string
      tcp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
      udp_port_range_list = list(object(
        {
          end_port   = number
          start_port = number
        }
      ))
    }
  ))
  default = []
}

variable "app_rule_target_group_filter_params" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
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

variable "isolation_rule_first_entity_filter_params" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}

variable "isolation_rule_second_entity_filter_params" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_network_security_rule" "this" {
  ad_rule_action                                = var.ad_rule_action
  ad_rule_target_group_default_internal_policy  = var.ad_rule_target_group_default_internal_policy
  ad_rule_target_group_filter_kind_list         = var.ad_rule_target_group_filter_kind_list
  ad_rule_target_group_filter_type              = var.ad_rule_target_group_filter_type
  ad_rule_target_group_peer_specification_type  = var.ad_rule_target_group_peer_specification_type
  allow_ipv6_traffic                            = var.allow_ipv6_traffic
  app_rule_action                               = var.app_rule_action
  app_rule_target_group_default_internal_policy = var.app_rule_target_group_default_internal_policy
  app_rule_target_group_filter_kind_list        = var.app_rule_target_group_filter_kind_list
  app_rule_target_group_filter_type             = var.app_rule_target_group_filter_type
  app_rule_target_group_peer_specification_type = var.app_rule_target_group_peer_specification_type
  description                                   = var.description
  is_policy_hitlog_enabled                      = var.is_policy_hitlog_enabled
  isolation_rule_action                         = var.isolation_rule_action
  isolation_rule_first_entity_filter_kind_list  = var.isolation_rule_first_entity_filter_kind_list
  isolation_rule_first_entity_filter_type       = var.isolation_rule_first_entity_filter_type
  isolation_rule_second_entity_filter_kind_list = var.isolation_rule_second_entity_filter_kind_list
  isolation_rule_second_entity_filter_type      = var.isolation_rule_second_entity_filter_type
  name                                          = var.name
  owner_reference                               = var.owner_reference
  project_reference                             = var.project_reference

  dynamic "ad_rule_inbound_allow_list" {
    for_each = var.ad_rule_inbound_allow_list
    content {
      expiration_time                  = ad_rule_inbound_allow_list.value["expiration_time"]
      filter_kind_list                 = ad_rule_inbound_allow_list.value["filter_kind_list"]
      filter_type                      = ad_rule_inbound_allow_list.value["filter_type"]
      ip_subnet                        = ad_rule_inbound_allow_list.value["ip_subnet"]
      ip_subnet_prefix_length          = ad_rule_inbound_allow_list.value["ip_subnet_prefix_length"]
      network_function_chain_reference = ad_rule_inbound_allow_list.value["network_function_chain_reference"]
      peer_specification_type          = ad_rule_inbound_allow_list.value["peer_specification_type"]
      protocol                         = ad_rule_inbound_allow_list.value["protocol"]

      dynamic "filter_params" {
        for_each = ad_rule_inbound_allow_list.value.filter_params
        content {
          name   = filter_params.value["name"]
          values = filter_params.value["values"]
        }
      }

      dynamic "icmp_type_code_list" {
        for_each = ad_rule_inbound_allow_list.value.icmp_type_code_list
        content {
          code = icmp_type_code_list.value["code"]
          type = icmp_type_code_list.value["type"]
        }
      }

      dynamic "tcp_port_range_list" {
        for_each = ad_rule_inbound_allow_list.value.tcp_port_range_list
        content {
          end_port   = tcp_port_range_list.value["end_port"]
          start_port = tcp_port_range_list.value["start_port"]
        }
      }

      dynamic "udp_port_range_list" {
        for_each = ad_rule_inbound_allow_list.value.udp_port_range_list
        content {
          end_port   = udp_port_range_list.value["end_port"]
          start_port = udp_port_range_list.value["start_port"]
        }
      }

    }
  }

  dynamic "ad_rule_outbound_allow_list" {
    for_each = var.ad_rule_outbound_allow_list
    content {
      expiration_time                  = ad_rule_outbound_allow_list.value["expiration_time"]
      filter_kind_list                 = ad_rule_outbound_allow_list.value["filter_kind_list"]
      filter_type                      = ad_rule_outbound_allow_list.value["filter_type"]
      ip_subnet                        = ad_rule_outbound_allow_list.value["ip_subnet"]
      ip_subnet_prefix_length          = ad_rule_outbound_allow_list.value["ip_subnet_prefix_length"]
      network_function_chain_reference = ad_rule_outbound_allow_list.value["network_function_chain_reference"]
      peer_specification_type          = ad_rule_outbound_allow_list.value["peer_specification_type"]
      protocol                         = ad_rule_outbound_allow_list.value["protocol"]

      dynamic "filter_params" {
        for_each = ad_rule_outbound_allow_list.value.filter_params
        content {
          name   = filter_params.value["name"]
          values = filter_params.value["values"]
        }
      }

      dynamic "icmp_type_code_list" {
        for_each = ad_rule_outbound_allow_list.value.icmp_type_code_list
        content {
          code = icmp_type_code_list.value["code"]
          type = icmp_type_code_list.value["type"]
        }
      }

      dynamic "tcp_port_range_list" {
        for_each = ad_rule_outbound_allow_list.value.tcp_port_range_list
        content {
          end_port   = tcp_port_range_list.value["end_port"]
          start_port = tcp_port_range_list.value["start_port"]
        }
      }

      dynamic "udp_port_range_list" {
        for_each = ad_rule_outbound_allow_list.value.udp_port_range_list
        content {
          end_port   = udp_port_range_list.value["end_port"]
          start_port = udp_port_range_list.value["start_port"]
        }
      }

    }
  }

  dynamic "ad_rule_target_group_filter_params" {
    for_each = var.ad_rule_target_group_filter_params
    content {
      name   = ad_rule_target_group_filter_params.value["name"]
      values = ad_rule_target_group_filter_params.value["values"]
    }
  }

  dynamic "app_rule_inbound_allow_list" {
    for_each = var.app_rule_inbound_allow_list
    content {
      expiration_time                  = app_rule_inbound_allow_list.value["expiration_time"]
      filter_kind_list                 = app_rule_inbound_allow_list.value["filter_kind_list"]
      filter_type                      = app_rule_inbound_allow_list.value["filter_type"]
      ip_subnet                        = app_rule_inbound_allow_list.value["ip_subnet"]
      ip_subnet_prefix_length          = app_rule_inbound_allow_list.value["ip_subnet_prefix_length"]
      network_function_chain_reference = app_rule_inbound_allow_list.value["network_function_chain_reference"]
      peer_specification_type          = app_rule_inbound_allow_list.value["peer_specification_type"]
      protocol                         = app_rule_inbound_allow_list.value["protocol"]

      dynamic "filter_params" {
        for_each = app_rule_inbound_allow_list.value.filter_params
        content {
          name   = filter_params.value["name"]
          values = filter_params.value["values"]
        }
      }

      dynamic "icmp_type_code_list" {
        for_each = app_rule_inbound_allow_list.value.icmp_type_code_list
        content {
          code = icmp_type_code_list.value["code"]
          type = icmp_type_code_list.value["type"]
        }
      }

      dynamic "tcp_port_range_list" {
        for_each = app_rule_inbound_allow_list.value.tcp_port_range_list
        content {
          end_port   = tcp_port_range_list.value["end_port"]
          start_port = tcp_port_range_list.value["start_port"]
        }
      }

      dynamic "udp_port_range_list" {
        for_each = app_rule_inbound_allow_list.value.udp_port_range_list
        content {
          end_port   = udp_port_range_list.value["end_port"]
          start_port = udp_port_range_list.value["start_port"]
        }
      }

    }
  }

  dynamic "app_rule_outbound_allow_list" {
    for_each = var.app_rule_outbound_allow_list
    content {
      expiration_time                  = app_rule_outbound_allow_list.value["expiration_time"]
      filter_kind_list                 = app_rule_outbound_allow_list.value["filter_kind_list"]
      filter_type                      = app_rule_outbound_allow_list.value["filter_type"]
      ip_subnet                        = app_rule_outbound_allow_list.value["ip_subnet"]
      ip_subnet_prefix_length          = app_rule_outbound_allow_list.value["ip_subnet_prefix_length"]
      network_function_chain_reference = app_rule_outbound_allow_list.value["network_function_chain_reference"]
      peer_specification_type          = app_rule_outbound_allow_list.value["peer_specification_type"]
      protocol                         = app_rule_outbound_allow_list.value["protocol"]

      dynamic "filter_params" {
        for_each = app_rule_outbound_allow_list.value.filter_params
        content {
          name   = filter_params.value["name"]
          values = filter_params.value["values"]
        }
      }

      dynamic "icmp_type_code_list" {
        for_each = app_rule_outbound_allow_list.value.icmp_type_code_list
        content {
          code = icmp_type_code_list.value["code"]
          type = icmp_type_code_list.value["type"]
        }
      }

      dynamic "tcp_port_range_list" {
        for_each = app_rule_outbound_allow_list.value.tcp_port_range_list
        content {
          end_port   = tcp_port_range_list.value["end_port"]
          start_port = tcp_port_range_list.value["start_port"]
        }
      }

      dynamic "udp_port_range_list" {
        for_each = app_rule_outbound_allow_list.value.udp_port_range_list
        content {
          end_port   = udp_port_range_list.value["end_port"]
          start_port = udp_port_range_list.value["start_port"]
        }
      }

    }
  }

  dynamic "app_rule_target_group_filter_params" {
    for_each = var.app_rule_target_group_filter_params
    content {
      name   = app_rule_target_group_filter_params.value["name"]
      values = app_rule_target_group_filter_params.value["values"]
    }
  }

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

  dynamic "isolation_rule_first_entity_filter_params" {
    for_each = var.isolation_rule_first_entity_filter_params
    content {
      name   = isolation_rule_first_entity_filter_params.value["name"]
      values = isolation_rule_first_entity_filter_params.value["values"]
    }
  }

  dynamic "isolation_rule_second_entity_filter_params" {
    for_each = var.isolation_rule_second_entity_filter_params
    content {
      name   = isolation_rule_second_entity_filter_params.value["name"]
      values = isolation_rule_second_entity_filter_params.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ad_rule_action" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.ad_rule_action
}

output "ad_rule_target_group_filter_kind_list" {
  description = "returns a list of string"
  value       = nutanix_network_security_rule.this.ad_rule_target_group_filter_kind_list
}

output "ad_rule_target_group_filter_type" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.ad_rule_target_group_filter_type
}

output "allow_ipv6_traffic" {
  description = "returns a bool"
  value       = nutanix_network_security_rule.this.allow_ipv6_traffic
}

output "api_version" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.api_version
}

output "app_rule_action" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.app_rule_action
}

output "app_rule_target_group_filter_kind_list" {
  description = "returns a list of string"
  value       = nutanix_network_security_rule.this.app_rule_target_group_filter_kind_list
}

output "app_rule_target_group_filter_type" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.app_rule_target_group_filter_type
}

output "description" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.id
}

output "is_policy_hitlog_enabled" {
  description = "returns a bool"
  value       = nutanix_network_security_rule.this.is_policy_hitlog_enabled
}

output "isolation_rule_action" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.isolation_rule_action
}

output "isolation_rule_first_entity_filter_kind_list" {
  description = "returns a list of string"
  value       = nutanix_network_security_rule.this.isolation_rule_first_entity_filter_kind_list
}

output "isolation_rule_first_entity_filter_type" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.isolation_rule_first_entity_filter_type
}

output "isolation_rule_second_entity_filter_kind_list" {
  description = "returns a list of string"
  value       = nutanix_network_security_rule.this.isolation_rule_second_entity_filter_kind_list
}

output "isolation_rule_second_entity_filter_type" {
  description = "returns a string"
  value       = nutanix_network_security_rule.this.isolation_rule_second_entity_filter_type
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_network_security_rule.this.metadata
}

output "owner_reference" {
  description = "returns a map of string"
  value       = nutanix_network_security_rule.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = nutanix_network_security_rule.this.project_reference
}

output "this" {
  value = nutanix_network_security_rule.this
}
```

[top](#index)