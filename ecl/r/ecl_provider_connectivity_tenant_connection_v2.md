# ecl_provider_connectivity_tenant_connection_v2

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
module "ecl_provider_connectivity_tenant_connection_v2" {
  source = "./modules/ecl/r/ecl_provider_connectivity_tenant_connection_v2"

  # description - (optional) is a type of string
  description = null
  # device_id - (required) is a type of string
  device_id = null
  # device_interface_id - (optional) is a type of string
  device_interface_id = null
  # device_type - (required) is a type of string
  device_type = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_connection_request_id - (required) is a type of string
  tenant_connection_request_id = null

  attachment_opts_baremetal = [{
    allowed_address_pairs = [{
      ip_address  = null
      mac_address = null
    }]
    fixed_ips = [{
      ip_address = null
      subnet_id  = null
    }]
    segmentation_id   = null
    segmentation_type = null
  }]

  attachment_opts_compute = [{
    allowed_address_pairs = [{
      ip_address  = null
      mac_address = null
    }]
    fixed_ips = [{
      ip_address = null
      subnet_id  = null
    }]
  }]

  attachment_opts_vna = [{
    fixed_ips = [{
      ip_address = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_id" {
  description = "(required)"
  type        = string
}

variable "device_interface_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_type" {
  description = "(required)"
  type        = string
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

variable "tenant_connection_request_id" {
  description = "(required)"
  type        = string
}

variable "attachment_opts_baremetal" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_address_pairs = list(object(
        {
          ip_address  = string
          mac_address = string
        }
      ))
      fixed_ips = list(object(
        {
          ip_address = string
          subnet_id  = string
        }
      ))
      segmentation_id   = number
      segmentation_type = string
    }
  ))
  default = []
}

variable "attachment_opts_compute" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_address_pairs = list(object(
        {
          ip_address  = string
          mac_address = string
        }
      ))
      fixed_ips = list(object(
        {
          ip_address = string
          subnet_id  = string
        }
      ))
    }
  ))
  default = []
}

variable "attachment_opts_vna" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fixed_ips = list(object(
        {
          ip_address = string
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
resource "ecl_provider_connectivity_tenant_connection_v2" "this" {
  description                  = var.description
  device_id                    = var.device_id
  device_interface_id          = var.device_interface_id
  device_type                  = var.device_type
  name                         = var.name
  tags                         = var.tags
  tenant_connection_request_id = var.tenant_connection_request_id

  dynamic "attachment_opts_baremetal" {
    for_each = var.attachment_opts_baremetal
    content {
      segmentation_id   = attachment_opts_baremetal.value["segmentation_id"]
      segmentation_type = attachment_opts_baremetal.value["segmentation_type"]

      dynamic "allowed_address_pairs" {
        for_each = attachment_opts_baremetal.value.allowed_address_pairs
        content {
          ip_address  = allowed_address_pairs.value["ip_address"]
          mac_address = allowed_address_pairs.value["mac_address"]
        }
      }

      dynamic "fixed_ips" {
        for_each = attachment_opts_baremetal.value.fixed_ips
        content {
          ip_address = fixed_ips.value["ip_address"]
          subnet_id  = fixed_ips.value["subnet_id"]
        }
      }

    }
  }

  dynamic "attachment_opts_compute" {
    for_each = var.attachment_opts_compute
    content {

      dynamic "allowed_address_pairs" {
        for_each = attachment_opts_compute.value.allowed_address_pairs
        content {
          ip_address  = allowed_address_pairs.value["ip_address"]
          mac_address = allowed_address_pairs.value["mac_address"]
        }
      }

      dynamic "fixed_ips" {
        for_each = attachment_opts_compute.value.fixed_ips
        content {
          ip_address = fixed_ips.value["ip_address"]
          subnet_id  = fixed_ips.value["subnet_id"]
        }
      }

    }
  }

  dynamic "attachment_opts_vna" {
    for_each = var.attachment_opts_vna
    content {

      dynamic "fixed_ips" {
        for_each = attachment_opts_vna.value.fixed_ips
        content {
          ip_address = fixed_ips.value["ip_address"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_v2.this.id
}

output "network_id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_v2.this.network_id
}

output "port_id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_v2.this.port_id
}

output "status" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_v2.this.tenant_id
}

output "tenant_id_other" {
  description = "returns a string"
  value       = ecl_provider_connectivity_tenant_connection_v2.this.tenant_id_other
}

output "this" {
  value = ecl_provider_connectivity_tenant_connection_v2.this
}
```

[top](#index)