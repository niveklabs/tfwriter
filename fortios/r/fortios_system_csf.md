# fortios_system_csf

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_csf" {
  source = "./modules/fortios/r/fortios_system_csf"

  # accept_auth_by_cert - (optional) is a type of string
  accept_auth_by_cert = null
  # authorization_request_type - (optional) is a type of string
  authorization_request_type = null
  # certificate - (optional) is a type of string
  certificate = null
  # configuration_sync - (optional) is a type of string
  configuration_sync = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fabric_object_unification - (optional) is a type of string
  fabric_object_unification = null
  # fixed_key - (optional) is a type of string
  fixed_key = null
  # group_name - (optional) is a type of string
  group_name = null
  # group_password - (optional) is a type of string
  group_password = null
  # management_ip - (optional) is a type of string
  management_ip = null
  # management_port - (optional) is a type of number
  management_port = null
  # saml_configuration_sync - (optional) is a type of string
  saml_configuration_sync = null
  # status - (required) is a type of string
  status = null
  # upstream_ip - (optional) is a type of string
  upstream_ip = null
  # upstream_port - (optional) is a type of number
  upstream_port = null

  fabric_device = [{
    access_token = null
    device_ip    = null
    device_type  = null
    https_port   = null
    login        = null
    name         = null
    password     = null
  }]

  trusted_list = [{
    action                   = null
    authorization_type       = null
    certificate              = null
    downstream_authorization = null
    ha_members               = null
    name                     = null
    serial                   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accept_auth_by_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorization_request_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configuration_sync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fabric_object_unification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fixed_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "saml_configuration_sync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "upstream_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upstream_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fabric_device" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_token = string
      device_ip    = string
      device_type  = string
      https_port   = number
      login        = string
      name         = string
      password     = string
    }
  ))
  default = []
}

variable "trusted_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action                   = string
      authorization_type       = string
      certificate              = string
      downstream_authorization = string
      ha_members               = string
      name                     = string
      serial                   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_csf" "this" {
  accept_auth_by_cert        = var.accept_auth_by_cert
  authorization_request_type = var.authorization_request_type
  certificate                = var.certificate
  configuration_sync         = var.configuration_sync
  dynamic_sort_subtable      = var.dynamic_sort_subtable
  fabric_object_unification  = var.fabric_object_unification
  fixed_key                  = var.fixed_key
  group_name                 = var.group_name
  group_password             = var.group_password
  management_ip              = var.management_ip
  management_port            = var.management_port
  saml_configuration_sync    = var.saml_configuration_sync
  status                     = var.status
  upstream_ip                = var.upstream_ip
  upstream_port              = var.upstream_port

  dynamic "fabric_device" {
    for_each = var.fabric_device
    content {
      access_token = fabric_device.value["access_token"]
      device_ip    = fabric_device.value["device_ip"]
      device_type  = fabric_device.value["device_type"]
      https_port   = fabric_device.value["https_port"]
      login        = fabric_device.value["login"]
      name         = fabric_device.value["name"]
      password     = fabric_device.value["password"]
    }
  }

  dynamic "trusted_list" {
    for_each = var.trusted_list
    content {
      action                   = trusted_list.value["action"]
      authorization_type       = trusted_list.value["authorization_type"]
      certificate              = trusted_list.value["certificate"]
      downstream_authorization = trusted_list.value["downstream_authorization"]
      ha_members               = trusted_list.value["ha_members"]
      name                     = trusted_list.value["name"]
      serial                   = trusted_list.value["serial"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accept_auth_by_cert" {
  description = "returns a string"
  value       = fortios_system_csf.this.accept_auth_by_cert
}

output "authorization_request_type" {
  description = "returns a string"
  value       = fortios_system_csf.this.authorization_request_type
}

output "certificate" {
  description = "returns a string"
  value       = fortios_system_csf.this.certificate
}

output "configuration_sync" {
  description = "returns a string"
  value       = fortios_system_csf.this.configuration_sync
}

output "fabric_object_unification" {
  description = "returns a string"
  value       = fortios_system_csf.this.fabric_object_unification
}

output "group_name" {
  description = "returns a string"
  value       = fortios_system_csf.this.group_name
}

output "id" {
  description = "returns a string"
  value       = fortios_system_csf.this.id
}

output "management_ip" {
  description = "returns a string"
  value       = fortios_system_csf.this.management_ip
}

output "management_port" {
  description = "returns a number"
  value       = fortios_system_csf.this.management_port
}

output "saml_configuration_sync" {
  description = "returns a string"
  value       = fortios_system_csf.this.saml_configuration_sync
}

output "upstream_ip" {
  description = "returns a string"
  value       = fortios_system_csf.this.upstream_ip
}

output "upstream_port" {
  description = "returns a number"
  value       = fortios_system_csf.this.upstream_port
}

output "this" {
  value = fortios_system_csf.this
}
```

[top](#index)