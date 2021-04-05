# ecl_network_load_balancer_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_load_balancer_v2" {
  source = "./modules/ecl/r/ecl_network_load_balancer_v2"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # default_gateway - (optional) is a type of string
  default_gateway = null
  # description - (optional) is a type of string
  description = null
  # load_balancer_plan_id - (required) is a type of string
  load_balancer_plan_id = null
  # name - (optional) is a type of string
  name = null
  # tenant_id - (optional) is a type of string
  tenant_id = null

  interfaces = [{
    description        = null
    id                 = null
    ip_address         = null
    name               = null
    network_id         = null
    slot_number        = null
    status             = null
    virtual_ip_address = null
    virtual_ip_properties = [{
      protocol = null
      vrid     = null
    }]
  }]

  syslog_servers = [{
    acl_logging                    = null
    appflow_logging                = null
    date_format                    = null
    description                    = null
    id                             = null
    ip_address                     = null
    log_facility                   = null
    log_level                      = null
    name                           = null
    port_number                    = null
    priority                       = null
    status                         = null
    tcp_logging                    = null
    tenant_id                      = null
    time_zone                      = null
    transport_type                 = null
    user_configurable_log_messages = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_plan_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description        = string
      id                 = string
      ip_address         = string
      name               = string
      network_id         = string
      slot_number        = number
      status             = string
      virtual_ip_address = string
      virtual_ip_properties = list(object(
        {
          protocol = string
          vrid     = number
        }
      ))
    }
  ))
  default = []
}

variable "syslog_servers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      acl_logging                    = string
      appflow_logging                = string
      date_format                    = string
      description                    = string
      id                             = string
      ip_address                     = string
      log_facility                   = string
      log_level                      = string
      name                           = string
      port_number                    = number
      priority                       = number
      status                         = string
      tcp_logging                    = string
      tenant_id                      = string
      time_zone                      = string
      transport_type                 = string
      user_configurable_log_messages = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_network_load_balancer_v2" "this" {
  availability_zone     = var.availability_zone
  default_gateway       = var.default_gateway
  description           = var.description
  load_balancer_plan_id = var.load_balancer_plan_id
  name                  = var.name
  tenant_id             = var.tenant_id

  dynamic "interfaces" {
    for_each = var.interfaces
    content {
      description        = interfaces.value["description"]
      ip_address         = interfaces.value["ip_address"]
      name               = interfaces.value["name"]
      network_id         = interfaces.value["network_id"]
      slot_number        = interfaces.value["slot_number"]
      virtual_ip_address = interfaces.value["virtual_ip_address"]

      dynamic "virtual_ip_properties" {
        for_each = interfaces.value.virtual_ip_properties
        content {
          protocol = virtual_ip_properties.value["protocol"]
          vrid     = virtual_ip_properties.value["vrid"]
        }
      }

    }
  }

  dynamic "syslog_servers" {
    for_each = var.syslog_servers
    content {
      acl_logging                    = syslog_servers.value["acl_logging"]
      appflow_logging                = syslog_servers.value["appflow_logging"]
      date_format                    = syslog_servers.value["date_format"]
      description                    = syslog_servers.value["description"]
      ip_address                     = syslog_servers.value["ip_address"]
      log_facility                   = syslog_servers.value["log_facility"]
      log_level                      = syslog_servers.value["log_level"]
      name                           = syslog_servers.value["name"]
      port_number                    = syslog_servers.value["port_number"]
      priority                       = syslog_servers.value["priority"]
      tcp_logging                    = syslog_servers.value["tcp_logging"]
      tenant_id                      = syslog_servers.value["tenant_id"]
      time_zone                      = syslog_servers.value["time_zone"]
      transport_type                 = syslog_servers.value["transport_type"]
      user_configurable_log_messages = syslog_servers.value["user_configurable_log_messages"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admin_password" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.admin_password
  sensitive   = true
}

output "admin_username" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.admin_username
}

output "id" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.id
}

output "status" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.tenant_id
}

output "user_password" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.user_password
  sensitive   = true
}

output "user_username" {
  description = "returns a string"
  value       = ecl_network_load_balancer_v2.this.user_username
}

output "this" {
  value = ecl_network_load_balancer_v2.this
}
```

[top](#index)