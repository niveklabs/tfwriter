# avi_ipaddrgroup

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_ipaddrgroup" {
  source = "./modules/avi/r/avi_ipaddrgroup"

  # apic_epg_name - (optional) is a type of string
  apic_epg_name = null
  # country_codes - (optional) is a type of list of string
  country_codes = []
  # description - (optional) is a type of string
  description = null
  # marathon_app_name - (optional) is a type of string
  marathon_app_name = null
  # marathon_service_port - (optional) is a type of number
  marathon_service_port = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  addrs = [{
    addr = null
    type = null
  }]

  ip_ports = [{
    hostname = null
    ip = [{
      addr = null
      type = null
    }]
    name = null
    port = null
  }]

  prefixes = [{
    ip_addr = [{
      addr = null
      type = null
    }]
    mask = null
  }]

  ranges = [{
    begin = [{
      addr = null
      type = null
    }]
    end = [{
      addr = null
      type = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "apic_epg_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "country_codes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "marathon_app_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "marathon_service_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "addrs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr = string
      type = string
    }
  ))
  default = []
}

variable "ip_ports" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname = string
      ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      name = string
      port = number
    }
  ))
  default = []
}

variable "prefixes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_addr = set(object(
        {
          addr = string
          type = string
        }
      ))
      mask = number
    }
  ))
  default = []
}

variable "ranges" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      begin = set(object(
        {
          addr = string
          type = string
        }
      ))
      end = set(object(
        {
          addr = string
          type = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_ipaddrgroup" "this" {
  apic_epg_name         = var.apic_epg_name
  country_codes         = var.country_codes
  description           = var.description
  marathon_app_name     = var.marathon_app_name
  marathon_service_port = var.marathon_service_port
  name                  = var.name
  tenant_ref            = var.tenant_ref
  uuid                  = var.uuid

  dynamic "addrs" {
    for_each = var.addrs
    content {
      addr = addrs.value["addr"]
      type = addrs.value["type"]
    }
  }

  dynamic "ip_ports" {
    for_each = var.ip_ports
    content {
      hostname = ip_ports.value["hostname"]
      name     = ip_ports.value["name"]
      port     = ip_ports.value["port"]

      dynamic "ip" {
        for_each = ip_ports.value.ip
        content {
          addr = ip.value["addr"]
          type = ip.value["type"]
        }
      }

    }
  }

  dynamic "prefixes" {
    for_each = var.prefixes
    content {
      mask = prefixes.value["mask"]

      dynamic "ip_addr" {
        for_each = prefixes.value.ip_addr
        content {
          addr = ip_addr.value["addr"]
          type = ip_addr.value["type"]
        }
      }

    }
  }

  dynamic "ranges" {
    for_each = var.ranges
    content {

      dynamic "begin" {
        for_each = ranges.value.begin
        content {
          addr = begin.value["addr"]
          type = begin.value["type"]
        }
      }

      dynamic "end" {
        for_each = ranges.value.end
        content {
          addr = end.value["addr"]
          type = end.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "apic_epg_name" {
  description = "returns a string"
  value       = avi_ipaddrgroup.this.apic_epg_name
}

output "description" {
  description = "returns a string"
  value       = avi_ipaddrgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_ipaddrgroup.this.id
}

output "marathon_app_name" {
  description = "returns a string"
  value       = avi_ipaddrgroup.this.marathon_app_name
}

output "marathon_service_port" {
  description = "returns a number"
  value       = avi_ipaddrgroup.this.marathon_service_port
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_ipaddrgroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_ipaddrgroup.this.uuid
}

output "this" {
  value = avi_ipaddrgroup.this
}
```

[top](#index)