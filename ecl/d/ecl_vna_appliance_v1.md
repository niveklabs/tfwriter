# ecl_vna_appliance_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/ecl/d/ecl_vna_appliance_v1"

  # appliance_type - (optional) is a type of string
  appliance_type = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # operation_status - (optional) is a type of string
  operation_status = null
  # os_login_status - (optional) is a type of string
  os_login_status = null
  # os_monitoring_status - (optional) is a type of string
  os_monitoring_status = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # virtual_network_appliance_id - (optional) is a type of string
  virtual_network_appliance_id = null
  # virtual_network_appliance_plan_id - (optional) is a type of string
  virtual_network_appliance_plan_id = null
  # vm_status - (optional) is a type of string
  vm_status = null

  interface_1_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_2_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_3_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_4_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_5_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_6_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_7_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]

  interface_8_info = [{
    description = null
    name        = null
    network_id  = null
    tags        = {}
    updatable   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "appliance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operation_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_login_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_monitoring_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_network_appliance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_network_appliance_plan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_1_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_2_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_3_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_4_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_5_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_6_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_7_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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

variable "interface_8_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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
```

[top](#index)

### Datasource

```terraform
data "ecl_vna_appliance_v1" "this" {
  appliance_type                    = var.appliance_type
  availability_zone                 = var.availability_zone
  description                       = var.description
  name                              = var.name
  operation_status                  = var.operation_status
  os_login_status                   = var.os_login_status
  os_monitoring_status              = var.os_monitoring_status
  tenant_id                         = var.tenant_id
  virtual_network_appliance_id      = var.virtual_network_appliance_id
  virtual_network_appliance_plan_id = var.virtual_network_appliance_plan_id
  vm_status                         = var.vm_status

  dynamic "interface_1_info" {
    for_each = var.interface_1_info
    content {
    }
  }

  dynamic "interface_2_info" {
    for_each = var.interface_2_info
    content {
    }
  }

  dynamic "interface_3_info" {
    for_each = var.interface_3_info
    content {
    }
  }

  dynamic "interface_4_info" {
    for_each = var.interface_4_info
    content {
    }
  }

  dynamic "interface_5_info" {
    for_each = var.interface_5_info
    content {
    }
  }

  dynamic "interface_6_info" {
    for_each = var.interface_6_info
    content {
    }
  }

  dynamic "interface_7_info" {
    for_each = var.interface_7_info
    content {
    }
  }

  dynamic "interface_8_info" {
    for_each = var.interface_8_info
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "appliance_type" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.appliance_type
}

output "availability_zone" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.availability_zone
}

output "description" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.id
}

output "interface_1_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_1_allowed_address_pairs
}

output "interface_1_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_1_fixed_ips
}

output "interface_2_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_2_allowed_address_pairs
}

output "interface_2_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_2_fixed_ips
}

output "interface_3_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_3_allowed_address_pairs
}

output "interface_3_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_3_fixed_ips
}

output "interface_4_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_4_allowed_address_pairs
}

output "interface_4_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_4_fixed_ips
}

output "interface_5_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_5_allowed_address_pairs
}

output "interface_5_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_5_fixed_ips
}

output "interface_6_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_6_allowed_address_pairs
}

output "interface_6_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_6_fixed_ips
}

output "interface_7_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_7_allowed_address_pairs
}

output "interface_7_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_7_fixed_ips
}

output "interface_8_allowed_address_pairs" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_8_allowed_address_pairs
}

output "interface_8_fixed_ips" {
  description = "returns a list of object"
  value       = data.ecl_vna_appliance_v1.this.interface_8_fixed_ips
}

output "name" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.name
}

output "operation_status" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.operation_status
}

output "os_login_status" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.os_login_status
}

output "os_monitoring_status" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.os_monitoring_status
}

output "tags" {
  description = "returns a map of string"
  value       = data.ecl_vna_appliance_v1.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.tenant_id
}

output "virtual_network_appliance_id" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.virtual_network_appliance_id
}

output "virtual_network_appliance_plan_id" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.virtual_network_appliance_plan_id
}

output "vm_status" {
  description = "returns a string"
  value       = data.ecl_vna_appliance_v1.this.vm_status
}

output "this" {
  value = ecl_vna_appliance_v1.this
}
```

[top](#index)