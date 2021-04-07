# equinix_network_bgp

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_network_bgp" {
  source = "./modules/equinix/r/equinix_network_bgp"

  # authentication_key - (optional) is a type of string
  authentication_key = null
  # connection_id - (required) is a type of string
  connection_id = null
  # local_asn - (required) is a type of number
  local_asn = null
  # local_ip_address - (required) is a type of string
  local_ip_address = null
  # remote_asn - (required) is a type of number
  remote_asn = null
  # remote_ip_address - (required) is a type of string
  remote_ip_address = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authentication_key" {
  description = "(optional) - Shared key used for BGP peer authentication"
  type        = string
  default     = null
}

variable "connection_id" {
  description = "(required) - Identifier of a connection established between network device and remote service provider that will be used for peering"
  type        = string
}

variable "local_asn" {
  description = "(required) - Local ASN number"
  type        = number
}

variable "local_ip_address" {
  description = "(required) - IP address in CIDR format of a local device"
  type        = string
}

variable "remote_asn" {
  description = "(required) - Remote ASN number"
  type        = number
}

variable "remote_ip_address" {
  description = "(required) - IP address of remote peer"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "equinix_network_bgp" "this" {
  # authentication_key - (optional) is a type of string
  authentication_key = var.authentication_key
  # connection_id - (required) is a type of string
  connection_id = var.connection_id
  # local_asn - (required) is a type of number
  local_asn = var.local_asn
  # local_ip_address - (required) is a type of string
  local_ip_address = var.local_ip_address
  # remote_asn - (required) is a type of number
  remote_asn = var.remote_asn
  # remote_ip_address - (required) is a type of string
  remote_ip_address = var.remote_ip_address

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "device_id" {
  description = "returns a string"
  value       = equinix_network_bgp.this.device_id
}

output "id" {
  description = "returns a string"
  value       = equinix_network_bgp.this.id
}

output "provisioning_status" {
  description = "returns a string"
  value       = equinix_network_bgp.this.provisioning_status
}

output "state" {
  description = "returns a string"
  value       = equinix_network_bgp.this.state
}

output "uuid" {
  description = "returns a string"
  value       = equinix_network_bgp.this.uuid
}

output "this" {
  value = equinix_network_bgp.this
}
```

[top](#index)