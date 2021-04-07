# cloudscale_server

[back](../cloudscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudscale = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudscale_server" {
  source = "./modules/cloudscale/r/cloudscale_server"

  # allow_stopping_for_update - (optional) is a type of bool
  allow_stopping_for_update = null
  # bulk_volume_size_gb - (optional) is a type of number
  bulk_volume_size_gb = null
  # flavor_slug - (required) is a type of string
  flavor_slug = null
  # image_slug - (required) is a type of string
  image_slug = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # server_group_ids - (optional) is a type of set of string
  server_group_ids = []
  # ssh_keys - (optional) is a type of set of string
  ssh_keys = []
  # status - (optional) is a type of string
  status = null
  # use_ipv6 - (optional) is a type of bool
  use_ipv6 = null
  # use_private_network - (optional) is a type of bool
  use_private_network = null
  # use_public_network - (optional) is a type of bool
  use_public_network = null
  # user_data - (optional) is a type of string
  user_data = null
  # volume_size_gb - (optional) is a type of number
  volume_size_gb = null
  # zone_slug - (optional) is a type of string
  zone_slug = null

  interfaces = [{
    addresses = [{
      address       = null
      gateway       = null
      prefix_length = null
      reverse_ptr   = null
      subnet_cidr   = null
      subnet_href   = null
      subnet_uuid   = null
      version       = null
    }]
    network_href = null
    network_name = null
    network_uuid = null
    no_address   = null
    type         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_stopping_for_update" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bulk_volume_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flavor_slug" {
  description = "(required)"
  type        = string
}

variable "image_slug" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ssh_keys" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_private_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_public_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone_slug" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addresses = list(object(
        {
          address       = string
          gateway       = string
          prefix_length = number
          reverse_ptr   = string
          subnet_cidr   = string
          subnet_href   = string
          subnet_uuid   = string
          version       = number
        }
      ))
      network_href = string
      network_name = string
      network_uuid = string
      no_address   = bool
      type         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudscale_server" "this" {
  # allow_stopping_for_update - (optional) is a type of bool
  allow_stopping_for_update = var.allow_stopping_for_update
  # bulk_volume_size_gb - (optional) is a type of number
  bulk_volume_size_gb = var.bulk_volume_size_gb
  # flavor_slug - (required) is a type of string
  flavor_slug = var.flavor_slug
  # image_slug - (required) is a type of string
  image_slug = var.image_slug
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # server_group_ids - (optional) is a type of set of string
  server_group_ids = var.server_group_ids
  # ssh_keys - (optional) is a type of set of string
  ssh_keys = var.ssh_keys
  # status - (optional) is a type of string
  status = var.status
  # use_ipv6 - (optional) is a type of bool
  use_ipv6 = var.use_ipv6
  # use_private_network - (optional) is a type of bool
  use_private_network = var.use_private_network
  # use_public_network - (optional) is a type of bool
  use_public_network = var.use_public_network
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # volume_size_gb - (optional) is a type of number
  volume_size_gb = var.volume_size_gb
  # zone_slug - (optional) is a type of string
  zone_slug = var.zone_slug

  dynamic "interfaces" {
    for_each = var.interfaces
    content {
      # network_uuid - (optional) is a type of string
      network_uuid = interfaces.value["network_uuid"]
      # no_address - (optional) is a type of bool
      no_address = interfaces.value["no_address"]
      # type - (required) is a type of string
      type = interfaces.value["type"]

      dynamic "addresses" {
        for_each = interfaces.value.addresses
        content {
          # address - (optional) is a type of string
          address = addresses.value["address"]
          # subnet_uuid - (optional) is a type of string
          subnet_uuid = addresses.value["subnet_uuid"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = cloudscale_server.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_server.this.id
}

output "private_ipv4_address" {
  description = "returns a string"
  value       = cloudscale_server.this.private_ipv4_address
}

output "public_ipv4_address" {
  description = "returns a string"
  value       = cloudscale_server.this.public_ipv4_address
}

output "public_ipv6_address" {
  description = "returns a string"
  value       = cloudscale_server.this.public_ipv6_address
}

output "server_groups" {
  description = "returns a list of object"
  value       = cloudscale_server.this.server_groups
}

output "ssh_fingerprints" {
  description = "returns a list of string"
  value       = cloudscale_server.this.ssh_fingerprints
}

output "ssh_host_keys" {
  description = "returns a list of string"
  value       = cloudscale_server.this.ssh_host_keys
}

output "status" {
  description = "returns a string"
  value       = cloudscale_server.this.status
}

output "volumes" {
  description = "returns a list of object"
  value       = cloudscale_server.this.volumes
}

output "zone_slug" {
  description = "returns a string"
  value       = cloudscale_server.this.zone_slug
}

output "this" {
  value = cloudscale_server.this
}
```

[top](#index)