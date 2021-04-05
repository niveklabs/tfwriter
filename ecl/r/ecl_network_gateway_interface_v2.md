# ecl_network_gateway_interface_v2

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
module "ecl_network_gateway_interface_v2" {
  source = "./modules/ecl/r/ecl_network_gateway_interface_v2"

  # aws_gw_id - (optional) is a type of string
  aws_gw_id = null
  # azure_gw_id - (optional) is a type of string
  azure_gw_id = null
  # description - (optional) is a type of string
  description = null
  # fic_gw_id - (optional) is a type of string
  fic_gw_id = null
  # gcp_gw_id - (optional) is a type of string
  gcp_gw_id = null
  # gw_vipv4 - (required) is a type of string
  gw_vipv4 = null
  # interdc_gw_id - (optional) is a type of string
  interdc_gw_id = null
  # internet_gw_id - (optional) is a type of string
  internet_gw_id = null
  # name - (optional) is a type of string
  name = null
  # netmask - (required) is a type of number
  netmask = null
  # network_id - (required) is a type of string
  network_id = null
  # primary_ipv4 - (required) is a type of string
  primary_ipv4 = null
  # region - (optional) is a type of string
  region = null
  # secondary_ipv4 - (required) is a type of string
  secondary_ipv4 = null
  # service_type - (required) is a type of string
  service_type = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # vpn_gw_id - (optional) is a type of string
  vpn_gw_id = null
  # vrid - (required) is a type of number
  vrid = null

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
variable "aws_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fic_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gw_vipv4" {
  description = "(required)"
  type        = string
}

variable "interdc_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "netmask" {
  description = "(required)"
  type        = number
}

variable "network_id" {
  description = "(required)"
  type        = string
}

variable "primary_ipv4" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_ipv4" {
  description = "(required)"
  type        = string
}

variable "service_type" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrid" {
  description = "(required)"
  type        = number
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
resource "ecl_network_gateway_interface_v2" "this" {
  aws_gw_id      = var.aws_gw_id
  azure_gw_id    = var.azure_gw_id
  description    = var.description
  fic_gw_id      = var.fic_gw_id
  gcp_gw_id      = var.gcp_gw_id
  gw_vipv4       = var.gw_vipv4
  interdc_gw_id  = var.interdc_gw_id
  internet_gw_id = var.internet_gw_id
  name           = var.name
  netmask        = var.netmask
  network_id     = var.network_id
  primary_ipv4   = var.primary_ipv4
  region         = var.region
  secondary_ipv4 = var.secondary_ipv4
  service_type   = var.service_type
  tenant_id      = var.tenant_id
  vpn_gw_id      = var.vpn_gw_id
  vrid           = var.vrid

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
output "gw_vipv6" {
  description = "returns a string"
  value       = ecl_network_gateway_interface_v2.this.gw_vipv6
}

output "id" {
  description = "returns a string"
  value       = ecl_network_gateway_interface_v2.this.id
}

output "primary_ipv6" {
  description = "returns a string"
  value       = ecl_network_gateway_interface_v2.this.primary_ipv6
}

output "region" {
  description = "returns a string"
  value       = ecl_network_gateway_interface_v2.this.region
}

output "secondary_ipv6" {
  description = "returns a string"
  value       = ecl_network_gateway_interface_v2.this.secondary_ipv6
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_gateway_interface_v2.this.tenant_id
}

output "this" {
  value = ecl_network_gateway_interface_v2.this
}
```

[top](#index)