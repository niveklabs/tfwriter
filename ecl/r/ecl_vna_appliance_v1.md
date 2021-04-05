# ecl_vna_appliance_v1

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
module "ecl_vna_appliance_v1" {
  source = "./modules/ecl/r/ecl_vna_appliance_v1"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # default_gateway - (optional) is a type of string
  default_gateway = null
  # description - (optional) is a type of string
  description = null
  # interface_1_no_allowed_address_pairs - (optional) is a type of bool
  interface_1_no_allowed_address_pairs = null
  # interface_1_no_fixed_ips - (optional) is a type of bool
  interface_1_no_fixed_ips = null
  # interface_2_no_allowed_address_pairs - (optional) is a type of bool
  interface_2_no_allowed_address_pairs = null
  # interface_2_no_fixed_ips - (optional) is a type of bool
  interface_2_no_fixed_ips = null
  # interface_3_no_allowed_address_pairs - (optional) is a type of bool
  interface_3_no_allowed_address_pairs = null
  # interface_3_no_fixed_ips - (optional) is a type of bool
  interface_3_no_fixed_ips = null
  # interface_4_no_allowed_address_pairs - (optional) is a type of bool
  interface_4_no_allowed_address_pairs = null
  # interface_4_no_fixed_ips - (optional) is a type of bool
  interface_4_no_fixed_ips = null
  # interface_5_no_allowed_address_pairs - (optional) is a type of bool
  interface_5_no_allowed_address_pairs = null
  # interface_5_no_fixed_ips - (optional) is a type of bool
  interface_5_no_fixed_ips = null
  # interface_6_no_allowed_address_pairs - (optional) is a type of bool
  interface_6_no_allowed_address_pairs = null
  # interface_6_no_fixed_ips - (optional) is a type of bool
  interface_6_no_fixed_ips = null
  # interface_7_no_allowed_address_pairs - (optional) is a type of bool
  interface_7_no_allowed_address_pairs = null
  # interface_7_no_fixed_ips - (optional) is a type of bool
  interface_7_no_fixed_ips = null
  # interface_8_no_allowed_address_pairs - (optional) is a type of bool
  interface_8_no_allowed_address_pairs = null
  # interface_8_no_fixed_ips - (optional) is a type of bool
  interface_8_no_fixed_ips = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # virtual_network_appliance_plan_id - (required) is a type of string
  virtual_network_appliance_plan_id = null

  interface_1_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_1_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_1_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_2_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_2_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_2_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_3_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_3_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_3_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_4_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_4_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_4_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_5_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_5_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_5_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_6_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_6_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_6_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_7_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_7_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_7_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_8_allowed_address_pairs = [{
    ip_address  = null
    mac_address = null
    type        = null
    vrid        = null
  }]

  interface_8_fixed_ips = [{
    ip_address = null
    subnet_id  = null
  }]

  interface_8_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
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

variable "interface_1_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_1_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_2_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_2_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_3_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_3_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_4_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_4_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_5_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_5_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_6_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_6_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_7_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_7_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_8_no_allowed_address_pairs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interface_8_no_fixed_ips" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
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

variable "virtual_network_appliance_plan_id" {
  description = "(required)"
  type        = string
}

variable "interface_1_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_1_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_1_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_2_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_2_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_2_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_3_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_3_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_3_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_4_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_4_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_4_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_5_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_5_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_5_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_6_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_6_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_6_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_7_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_7_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_7_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
    }
  ))
  default = []
}

variable "interface_8_allowed_address_pairs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      type        = string
      vrid        = string
    }
  ))
  default = []
}

variable "interface_8_fixed_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = string
      subnet_id  = string
    }
  ))
  default = []
}

variable "interface_8_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      name        = string
      network_id  = string
      tags        = map(string)
      updatable   = bool
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
resource "ecl_vna_appliance_v1" "this" {
  availability_zone                    = var.availability_zone
  default_gateway                      = var.default_gateway
  description                          = var.description
  interface_1_no_allowed_address_pairs = var.interface_1_no_allowed_address_pairs
  interface_1_no_fixed_ips             = var.interface_1_no_fixed_ips
  interface_2_no_allowed_address_pairs = var.interface_2_no_allowed_address_pairs
  interface_2_no_fixed_ips             = var.interface_2_no_fixed_ips
  interface_3_no_allowed_address_pairs = var.interface_3_no_allowed_address_pairs
  interface_3_no_fixed_ips             = var.interface_3_no_fixed_ips
  interface_4_no_allowed_address_pairs = var.interface_4_no_allowed_address_pairs
  interface_4_no_fixed_ips             = var.interface_4_no_fixed_ips
  interface_5_no_allowed_address_pairs = var.interface_5_no_allowed_address_pairs
  interface_5_no_fixed_ips             = var.interface_5_no_fixed_ips
  interface_6_no_allowed_address_pairs = var.interface_6_no_allowed_address_pairs
  interface_6_no_fixed_ips             = var.interface_6_no_fixed_ips
  interface_7_no_allowed_address_pairs = var.interface_7_no_allowed_address_pairs
  interface_7_no_fixed_ips             = var.interface_7_no_fixed_ips
  interface_8_no_allowed_address_pairs = var.interface_8_no_allowed_address_pairs
  interface_8_no_fixed_ips             = var.interface_8_no_fixed_ips
  name                                 = var.name
  tags                                 = var.tags
  tenant_id                            = var.tenant_id
  virtual_network_appliance_plan_id    = var.virtual_network_appliance_plan_id

  dynamic "interface_1_allowed_address_pairs" {
    for_each = var.interface_1_allowed_address_pairs
    content {
      ip_address  = interface_1_allowed_address_pairs.value["ip_address"]
      mac_address = interface_1_allowed_address_pairs.value["mac_address"]
      type        = interface_1_allowed_address_pairs.value["type"]
      vrid        = interface_1_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_1_fixed_ips" {
    for_each = var.interface_1_fixed_ips
    content {
      ip_address = interface_1_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_1_info" {
    for_each = var.interface_1_info
    content {
      description = interface_1_info.value["description"]
      name        = interface_1_info.value["name"]
      network_id  = interface_1_info.value["network_id"]
      tags        = interface_1_info.value["tags"]
    }
  }

  dynamic "interface_2_allowed_address_pairs" {
    for_each = var.interface_2_allowed_address_pairs
    content {
      ip_address  = interface_2_allowed_address_pairs.value["ip_address"]
      mac_address = interface_2_allowed_address_pairs.value["mac_address"]
      type        = interface_2_allowed_address_pairs.value["type"]
      vrid        = interface_2_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_2_fixed_ips" {
    for_each = var.interface_2_fixed_ips
    content {
      ip_address = interface_2_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_2_info" {
    for_each = var.interface_2_info
    content {
      description = interface_2_info.value["description"]
      name        = interface_2_info.value["name"]
      network_id  = interface_2_info.value["network_id"]
      tags        = interface_2_info.value["tags"]
    }
  }

  dynamic "interface_3_allowed_address_pairs" {
    for_each = var.interface_3_allowed_address_pairs
    content {
      ip_address  = interface_3_allowed_address_pairs.value["ip_address"]
      mac_address = interface_3_allowed_address_pairs.value["mac_address"]
      type        = interface_3_allowed_address_pairs.value["type"]
      vrid        = interface_3_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_3_fixed_ips" {
    for_each = var.interface_3_fixed_ips
    content {
      ip_address = interface_3_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_3_info" {
    for_each = var.interface_3_info
    content {
      description = interface_3_info.value["description"]
      name        = interface_3_info.value["name"]
      network_id  = interface_3_info.value["network_id"]
      tags        = interface_3_info.value["tags"]
    }
  }

  dynamic "interface_4_allowed_address_pairs" {
    for_each = var.interface_4_allowed_address_pairs
    content {
      ip_address  = interface_4_allowed_address_pairs.value["ip_address"]
      mac_address = interface_4_allowed_address_pairs.value["mac_address"]
      type        = interface_4_allowed_address_pairs.value["type"]
      vrid        = interface_4_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_4_fixed_ips" {
    for_each = var.interface_4_fixed_ips
    content {
      ip_address = interface_4_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_4_info" {
    for_each = var.interface_4_info
    content {
      description = interface_4_info.value["description"]
      name        = interface_4_info.value["name"]
      network_id  = interface_4_info.value["network_id"]
      tags        = interface_4_info.value["tags"]
    }
  }

  dynamic "interface_5_allowed_address_pairs" {
    for_each = var.interface_5_allowed_address_pairs
    content {
      ip_address  = interface_5_allowed_address_pairs.value["ip_address"]
      mac_address = interface_5_allowed_address_pairs.value["mac_address"]
      type        = interface_5_allowed_address_pairs.value["type"]
      vrid        = interface_5_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_5_fixed_ips" {
    for_each = var.interface_5_fixed_ips
    content {
      ip_address = interface_5_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_5_info" {
    for_each = var.interface_5_info
    content {
      description = interface_5_info.value["description"]
      name        = interface_5_info.value["name"]
      network_id  = interface_5_info.value["network_id"]
      tags        = interface_5_info.value["tags"]
    }
  }

  dynamic "interface_6_allowed_address_pairs" {
    for_each = var.interface_6_allowed_address_pairs
    content {
      ip_address  = interface_6_allowed_address_pairs.value["ip_address"]
      mac_address = interface_6_allowed_address_pairs.value["mac_address"]
      type        = interface_6_allowed_address_pairs.value["type"]
      vrid        = interface_6_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_6_fixed_ips" {
    for_each = var.interface_6_fixed_ips
    content {
      ip_address = interface_6_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_6_info" {
    for_each = var.interface_6_info
    content {
      description = interface_6_info.value["description"]
      name        = interface_6_info.value["name"]
      network_id  = interface_6_info.value["network_id"]
      tags        = interface_6_info.value["tags"]
    }
  }

  dynamic "interface_7_allowed_address_pairs" {
    for_each = var.interface_7_allowed_address_pairs
    content {
      ip_address  = interface_7_allowed_address_pairs.value["ip_address"]
      mac_address = interface_7_allowed_address_pairs.value["mac_address"]
      type        = interface_7_allowed_address_pairs.value["type"]
      vrid        = interface_7_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_7_fixed_ips" {
    for_each = var.interface_7_fixed_ips
    content {
      ip_address = interface_7_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_7_info" {
    for_each = var.interface_7_info
    content {
      description = interface_7_info.value["description"]
      name        = interface_7_info.value["name"]
      network_id  = interface_7_info.value["network_id"]
      tags        = interface_7_info.value["tags"]
    }
  }

  dynamic "interface_8_allowed_address_pairs" {
    for_each = var.interface_8_allowed_address_pairs
    content {
      ip_address  = interface_8_allowed_address_pairs.value["ip_address"]
      mac_address = interface_8_allowed_address_pairs.value["mac_address"]
      type        = interface_8_allowed_address_pairs.value["type"]
      vrid        = interface_8_allowed_address_pairs.value["vrid"]
    }
  }

  dynamic "interface_8_fixed_ips" {
    for_each = var.interface_8_fixed_ips
    content {
      ip_address = interface_8_fixed_ips.value["ip_address"]
    }
  }

  dynamic "interface_8_info" {
    for_each = var.interface_8_info
    content {
      description = interface_8_info.value["description"]
      name        = interface_8_info.value["name"]
      network_id  = interface_8_info.value["network_id"]
      tags        = interface_8_info.value["tags"]
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
output "availability_zone" {
  description = "returns a string"
  value       = ecl_vna_appliance_v1.this.availability_zone
}

output "id" {
  description = "returns a string"
  value       = ecl_vna_appliance_v1.this.id
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_vna_appliance_v1.this.tenant_id
}

output "this" {
  value = ecl_vna_appliance_v1.this
}
```

[top](#index)