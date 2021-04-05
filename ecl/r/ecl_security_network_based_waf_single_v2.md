# ecl_security_network_based_waf_single_v2

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
module "ecl_security_network_based_waf_single_v2" {
  source = "./modules/ecl/r/ecl_security_network_based_waf_single_v2"

  # az_group - (required) is a type of string
  az_group = null
  # license_kind - (required) is a type of string
  license_kind = null
  # locale - (optional) is a type of string
  locale = null
  # operating_mode - (optional) is a type of string
  operating_mode = null
  # tenant_id - (required) is a type of string
  tenant_id = null

  port = [{
    comment           = null
    enable            = null
    ip_address        = null
    ip_address_prefix = null
    mtu               = null
    network_id        = null
    subnet_id         = null
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
variable "az_group" {
  description = "(required)"
  type        = string
}

variable "license_kind" {
  description = "(required)"
  type        = string
}

variable "locale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operating_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      comment           = string
      enable            = string
      ip_address        = string
      ip_address_prefix = number
      mtu               = string
      network_id        = string
      subnet_id         = string
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
resource "ecl_security_network_based_waf_single_v2" "this" {
  az_group       = var.az_group
  license_kind   = var.license_kind
  locale         = var.locale
  operating_mode = var.operating_mode
  tenant_id      = var.tenant_id

  dynamic "port" {
    for_each = var.port
    content {
      comment           = port.value["comment"]
      enable            = port.value["enable"]
      ip_address        = port.value["ip_address"]
      ip_address_prefix = port.value["ip_address_prefix"]
      mtu               = port.value["mtu"]
      network_id        = port.value["network_id"]
      subnet_id         = port.value["subnet_id"]
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
output "id" {
  description = "returns a string"
  value       = ecl_security_network_based_waf_single_v2.this.id
}

output "this" {
  value = ecl_security_network_based_waf_single_v2.this
}
```

[top](#index)