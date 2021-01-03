# oci_load_balancer_load_balancer

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_load_balancer" {
  source = "./modules/oci/r/oci_load_balancer_load_balancer"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # ip_mode - (optional) is a type of string
  ip_mode = null
  # is_private - (optional) is a type of bool
  is_private = null
  # network_security_group_ids - (optional) is a type of set of string
  network_security_group_ids = []
  # shape - (required) is a type of string
  shape = null
  # subnet_ids - (required) is a type of list of string
  subnet_ids = []

  reserved_ips = [{
    id = null
  }]

  shape_details = [{
    maximum_bandwidth_in_mbps = null
    minimum_bandwidth_in_mbps = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ip_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_private" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "network_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "subnet_ids" {
  description = "(required)"
  type        = list(string)
}

variable "reserved_ips" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}

variable "shape_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      maximum_bandwidth_in_mbps = number
      minimum_bandwidth_in_mbps = number
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
resource "oci_load_balancer_load_balancer" "this" {
  compartment_id             = var.compartment_id
  defined_tags               = var.defined_tags
  display_name               = var.display_name
  freeform_tags              = var.freeform_tags
  ip_mode                    = var.ip_mode
  is_private                 = var.is_private
  network_security_group_ids = var.network_security_group_ids
  shape                      = var.shape
  subnet_ids                 = var.subnet_ids

  dynamic "reserved_ips" {
    for_each = var.reserved_ips
    content {
      id = reserved_ips.value["id"]
    }
  }

  dynamic "shape_details" {
    for_each = var.shape_details
    content {
      maximum_bandwidth_in_mbps = shape_details.value["maximum_bandwidth_in_mbps"]
      minimum_bandwidth_in_mbps = shape_details.value["minimum_bandwidth_in_mbps"]
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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_load_balancer_load_balancer.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_load_balancer_load_balancer.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_load_balancer_load_balancer.this.id
}

output "ip_address_details" {
  description = "returns a list of object"
  value       = oci_load_balancer_load_balancer.this.ip_address_details
}

output "ip_addresses" {
  description = "returns a list of string"
  value       = oci_load_balancer_load_balancer.this.ip_addresses
}

output "ip_mode" {
  description = "returns a string"
  value       = oci_load_balancer_load_balancer.this.ip_mode
}

output "is_private" {
  description = "returns a bool"
  value       = oci_load_balancer_load_balancer.this.is_private
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_load_balancer.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_load_balancer_load_balancer.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_load_balancer_load_balancer.this.time_created
}

output "this" {
  value = oci_load_balancer_load_balancer.this
}
```

[top](#index)