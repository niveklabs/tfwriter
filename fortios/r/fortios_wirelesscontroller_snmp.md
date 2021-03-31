# fortios_wirelesscontroller_snmp

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
module "fortios_wirelesscontroller_snmp" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_snmp"

  # contact_info - (optional) is a type of string
  contact_info = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # engine_id - (optional) is a type of string
  engine_id = null
  # trap_high_cpu_threshold - (optional) is a type of number
  trap_high_cpu_threshold = null
  # trap_high_mem_threshold - (optional) is a type of number
  trap_high_mem_threshold = null

  community = [{
    hosts = [{
      id = null
      ip = null
    }]
    id               = null
    name             = null
    query_v1_status  = null
    query_v2c_status = null
    status           = null
    trap_v1_status   = null
    trap_v2c_status  = null
  }]

  user = [{
    auth_proto     = null
    auth_pwd       = null
    name           = null
    notify_hosts   = null
    priv_proto     = null
    priv_pwd       = null
    queries        = null
    security_level = null
    status         = null
    trap_status    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "contact_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trap_high_cpu_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_high_mem_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "community" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hosts = list(object(
        {
          id = number
          ip = string
        }
      ))
      id               = number
      name             = string
      query_v1_status  = string
      query_v2c_status = string
      status           = string
      trap_v1_status   = string
      trap_v2c_status  = string
    }
  ))
  default = []
}

variable "user" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_proto     = string
      auth_pwd       = string
      name           = string
      notify_hosts   = string
      priv_proto     = string
      priv_pwd       = string
      queries        = string
      security_level = string
      status         = string
      trap_status    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_snmp" "this" {
  contact_info            = var.contact_info
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  engine_id               = var.engine_id
  trap_high_cpu_threshold = var.trap_high_cpu_threshold
  trap_high_mem_threshold = var.trap_high_mem_threshold

  dynamic "community" {
    for_each = var.community
    content {
      id               = community.value["id"]
      name             = community.value["name"]
      query_v1_status  = community.value["query_v1_status"]
      query_v2c_status = community.value["query_v2c_status"]
      status           = community.value["status"]
      trap_v1_status   = community.value["trap_v1_status"]
      trap_v2c_status  = community.value["trap_v2c_status"]

      dynamic "hosts" {
        for_each = community.value.hosts
        content {
          id = hosts.value["id"]
          ip = hosts.value["ip"]
        }
      }

    }
  }

  dynamic "user" {
    for_each = var.user
    content {
      auth_proto     = user.value["auth_proto"]
      auth_pwd       = user.value["auth_pwd"]
      name           = user.value["name"]
      notify_hosts   = user.value["notify_hosts"]
      priv_proto     = user.value["priv_proto"]
      priv_pwd       = user.value["priv_pwd"]
      queries        = user.value["queries"]
      security_level = user.value["security_level"]
      status         = user.value["status"]
      trap_status    = user.value["trap_status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "contact_info" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_snmp.this.contact_info
}

output "engine_id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_snmp.this.engine_id
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_snmp.this.id
}

output "trap_high_cpu_threshold" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_snmp.this.trap_high_cpu_threshold
}

output "trap_high_mem_threshold" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_snmp.this.trap_high_mem_threshold
}

output "this" {
  value = fortios_wirelesscontroller_snmp.this
}
```

[top](#index)