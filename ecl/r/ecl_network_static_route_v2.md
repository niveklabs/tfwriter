# ecl_network_static_route_v2

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
module "ecl_network_static_route_v2" {
  source = "./modules/ecl/r/ecl_network_static_route_v2"

  # aws_gw_id - (optional) is a type of string
  aws_gw_id = null
  # azure_gw_id - (optional) is a type of string
  azure_gw_id = null
  # description - (optional) is a type of string
  description = null
  # destination - (required) is a type of string
  destination = null
  # fic_gw_id - (optional) is a type of string
  fic_gw_id = null
  # gcp_gw_id - (optional) is a type of string
  gcp_gw_id = null
  # interdc_gw_id - (optional) is a type of string
  interdc_gw_id = null
  # internet_gw_id - (optional) is a type of string
  internet_gw_id = null
  # name - (optional) is a type of string
  name = null
  # nexthop - (required) is a type of string
  nexthop = null
  # region - (optional) is a type of string
  region = null
  # service_type - (required) is a type of string
  service_type = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # vpn_gw_id - (optional) is a type of string
  vpn_gw_id = null

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

variable "destination" {
  description = "(required)"
  type        = string
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

variable "nexthop" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "ecl_network_static_route_v2" "this" {
  aws_gw_id      = var.aws_gw_id
  azure_gw_id    = var.azure_gw_id
  description    = var.description
  destination    = var.destination
  fic_gw_id      = var.fic_gw_id
  gcp_gw_id      = var.gcp_gw_id
  interdc_gw_id  = var.interdc_gw_id
  internet_gw_id = var.internet_gw_id
  name           = var.name
  nexthop        = var.nexthop
  region         = var.region
  service_type   = var.service_type
  tenant_id      = var.tenant_id
  vpn_gw_id      = var.vpn_gw_id

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
  value       = ecl_network_static_route_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_network_static_route_v2.this.region
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_static_route_v2.this.tenant_id
}

output "this" {
  value = ecl_network_static_route_v2.this
}
```

[top](#index)