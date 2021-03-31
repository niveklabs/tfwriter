# ecl_security_network_based_device_ha_v1

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
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_security_network_based_device_ha_v1" {
  source = "./modules/ecl/r/ecl_security_network_based_device_ha_v1"

  # host_1_az_group - (required) is a type of string
  host_1_az_group = null
  # host_2_az_group - (required) is a type of string
  host_2_az_group = null
  # license_kind - (required) is a type of string
  license_kind = null
  # locale - (optional) is a type of string
  locale = null
  # operating_mode - (required) is a type of string
  operating_mode = null
  # tenant_id - (required) is a type of string
  tenant_id = null

  ha_link_1 = [{
    host_1_ip_address = null
    host_2_ip_address = null
    network_id        = null
    subnet_id         = null
  }]

  ha_link_2 = [{
    host_1_ip_address = null
    host_2_ip_address = null
    network_id        = null
    subnet_id         = null
  }]

  port = [{
    comment                  = null
    enable                   = null
    enable_ping              = null
    host_1_ip_address        = null
    host_1_ip_address_prefix = null
    host_2_ip_address        = null
    host_2_ip_address_prefix = null
    mtu                      = null
    network_id               = null
    preempt                  = null
    subnet_id                = null
    vrrp_grp_id              = null
    vrrp_id                  = null
    vrrp_ip_address          = null
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
variable "host_1_az_group" {
  description = "(required)"
  type        = string
}

variable "host_2_az_group" {
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
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "ha_link_1" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      host_1_ip_address = string
      host_2_ip_address = string
      network_id        = string
      subnet_id         = string
    }
  ))
}

variable "ha_link_2" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      host_1_ip_address = string
      host_2_ip_address = string
      network_id        = string
      subnet_id         = string
    }
  ))
}

variable "port" {
  description = "nested block: NestingList, min items: 0, max items: 7"
  type = set(object(
    {
      comment                  = string
      enable                   = string
      enable_ping              = string
      host_1_ip_address        = string
      host_1_ip_address_prefix = number
      host_2_ip_address        = string
      host_2_ip_address_prefix = number
      mtu                      = string
      network_id               = string
      preempt                  = string
      subnet_id                = string
      vrrp_grp_id              = string
      vrrp_id                  = string
      vrrp_ip_address          = string
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
resource "ecl_security_network_based_device_ha_v1" "this" {
  host_1_az_group = var.host_1_az_group
  host_2_az_group = var.host_2_az_group
  license_kind    = var.license_kind
  locale          = var.locale
  operating_mode  = var.operating_mode
  tenant_id       = var.tenant_id

  dynamic "ha_link_1" {
    for_each = var.ha_link_1
    content {
      host_1_ip_address = ha_link_1.value["host_1_ip_address"]
      host_2_ip_address = ha_link_1.value["host_2_ip_address"]
      network_id        = ha_link_1.value["network_id"]
      subnet_id         = ha_link_1.value["subnet_id"]
    }
  }

  dynamic "ha_link_2" {
    for_each = var.ha_link_2
    content {
      host_1_ip_address = ha_link_2.value["host_1_ip_address"]
      host_2_ip_address = ha_link_2.value["host_2_ip_address"]
      network_id        = ha_link_2.value["network_id"]
      subnet_id         = ha_link_2.value["subnet_id"]
    }
  }

  dynamic "port" {
    for_each = var.port
    content {
      comment                  = port.value["comment"]
      enable                   = port.value["enable"]
      enable_ping              = port.value["enable_ping"]
      host_1_ip_address        = port.value["host_1_ip_address"]
      host_1_ip_address_prefix = port.value["host_1_ip_address_prefix"]
      host_2_ip_address        = port.value["host_2_ip_address"]
      host_2_ip_address_prefix = port.value["host_2_ip_address_prefix"]
      mtu                      = port.value["mtu"]
      network_id               = port.value["network_id"]
      preempt                  = port.value["preempt"]
      subnet_id                = port.value["subnet_id"]
      vrrp_grp_id              = port.value["vrrp_grp_id"]
      vrrp_id                  = port.value["vrrp_id"]
      vrrp_ip_address          = port.value["vrrp_ip_address"]
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
  value       = ecl_security_network_based_device_ha_v1.this.id
}

output "this" {
  value = ecl_security_network_based_device_ha_v1.this
}
```

[top](#index)