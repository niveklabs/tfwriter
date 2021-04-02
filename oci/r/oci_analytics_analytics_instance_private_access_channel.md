# oci_analytics_analytics_instance_private_access_channel

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_analytics_analytics_instance_private_access_channel" {
  source = "./modules/oci/r/oci_analytics_analytics_instance_private_access_channel"

  # analytics_instance_id - (required) is a type of string
  analytics_instance_id = null
  # display_name - (required) is a type of string
  display_name = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # vcn_id - (required) is a type of string
  vcn_id = null

  private_source_dns_zones = [{
    description = null
    dns_zone    = null
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
variable "analytics_instance_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "vcn_id" {
  description = "(required)"
  type        = string
}

variable "private_source_dns_zones" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      description = string
      dns_zone    = string
    }
  ))
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
resource "oci_analytics_analytics_instance_private_access_channel" "this" {
  analytics_instance_id = var.analytics_instance_id
  display_name          = var.display_name
  subnet_id             = var.subnet_id
  vcn_id                = var.vcn_id

  dynamic "private_source_dns_zones" {
    for_each = var.private_source_dns_zones
    content {
      description = private_source_dns_zones.value["description"]
      dns_zone    = private_source_dns_zones.value["dns_zone"]
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
output "egress_source_ip_addresses" {
  description = "returns a list of string"
  value       = oci_analytics_analytics_instance_private_access_channel.this.egress_source_ip_addresses
}

output "id" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance_private_access_channel.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance_private_access_channel.this.ip_address
}

output "key" {
  description = "returns a string"
  value       = oci_analytics_analytics_instance_private_access_channel.this.key
}

output "this" {
  value = oci_analytics_analytics_instance_private_access_channel.this
}
```

[top](#index)