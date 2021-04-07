# ecl_network_port_v2

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
module "ecl_network_port_v2" {
  source = "./modules/ecl/r/ecl_network_port_v2"

  # admin_state_up - (optional) is a type of bool
  admin_state_up = null
  # description - (optional) is a type of string
  description = null
  # device_id - (optional) is a type of string
  device_id = null
  # device_owner - (optional) is a type of string
  device_owner = null
  # mac_address - (optional) is a type of string
  mac_address = null
  # name - (optional) is a type of string
  name = null
  # network_id - (required) is a type of string
  network_id = null
  # no_fixed_ip - (optional) is a type of bool
  no_fixed_ip = null
  # region - (optional) is a type of string
  region = null
  # segmentation_id - (optional) is a type of number
  segmentation_id = null
  # segmentation_type - (optional) is a type of string
  segmentation_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_id - (optional) is a type of string
  tenant_id = null

  allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
  }]

  fixed_ip = [{
    ip_address = null
    subnet_id  = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_state_up" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_id" {
  description = "(required)"
  type        = string
}

variable "no_fixed_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "segmentation_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "segmentation_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_address_pairs" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
    }
  ))
  default = []
}

variable "fixed_ip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_network_port_v2" "this" {
  # admin_state_up - (optional) is a type of bool
  admin_state_up = var.admin_state_up
  # description - (optional) is a type of string
  description = var.description
  # device_id - (optional) is a type of string
  device_id = var.device_id
  # device_owner - (optional) is a type of string
  device_owner = var.device_owner
  # mac_address - (optional) is a type of string
  mac_address = var.mac_address
  # name - (optional) is a type of string
  name = var.name
  # network_id - (required) is a type of string
  network_id = var.network_id
  # no_fixed_ip - (optional) is a type of bool
  no_fixed_ip = var.no_fixed_ip
  # region - (optional) is a type of string
  region = var.region
  # segmentation_id - (optional) is a type of number
  segmentation_id = var.segmentation_id
  # segmentation_type - (optional) is a type of string
  segmentation_type = var.segmentation_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tenant_id - (optional) is a type of string
  tenant_id = var.tenant_id

  dynamic "allowed_address_pairs" {
    for_each = var.allowed_address_pairs
    content {
      # ip_address - (required) is a type of string
      ip_address = allowed_address_pairs.value["ip_address"]
      # mac_address - (optional) is a type of string
      mac_address = allowed_address_pairs.value["mac_address"]
    }
  }

  dynamic "fixed_ip" {
    for_each = var.fixed_ip
    content {
      # ip_address - (optional) is a type of string
      ip_address = fixed_ip.value["ip_address"]
      # subnet_id - (required) is a type of string
      subnet_id = fixed_ip.value["subnet_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admin_state_up" {
  description = "returns a bool"
  value       = ecl_network_port_v2.this.admin_state_up
}

output "all_fixed_ips" {
  description = "returns a list of string"
  value       = ecl_network_port_v2.this.all_fixed_ips
}

output "device_id" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.device_id
}

output "device_owner" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.device_owner
}

output "id" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.id
}

output "mac_address" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.mac_address
}

output "managed_by_service" {
  description = "returns a bool"
  value       = ecl_network_port_v2.this.managed_by_service
}

output "region" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.region
}

output "segmentation_id" {
  description = "returns a number"
  value       = ecl_network_port_v2.this.segmentation_id
}

output "segmentation_type" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.segmentation_type
}

output "status" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_port_v2.this.tenant_id
}

output "this" {
  value = ecl_network_port_v2.this
}
```

[top](#index)