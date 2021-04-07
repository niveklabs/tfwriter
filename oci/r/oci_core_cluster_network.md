# oci_core_cluster_network

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_cluster_network" {
  source = "./modules/oci/r/oci_core_cluster_network"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

  instance_pools = [{
    compartment_id            = null
    defined_tags              = {}
    display_name              = null
    freeform_tags             = {}
    id                        = null
    instance_configuration_id = null
    load_balancers = [{
      backend_set_name = null
      id               = null
      instance_pool_id = null
      load_balancer_id = null
      port             = null
      state            = null
      vnic_selection   = null
    }]
    placement_configurations = [{
      availability_domain = null
      fault_domains       = []
      primary_subnet_id   = null
      secondary_vnic_subnets = [{
        display_name = null
        subnet_id    = null
      }]
    }]
    size         = null
    state        = null
    time_created = null
  }]

  placement_configuration = [{
    availability_domain = null
    primary_subnet_id   = null
    secondary_vnic_subnets = [{
      display_name = null
      subnet_id    = null
    }]
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "instance_pools" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      compartment_id            = string
      defined_tags              = map(string)
      display_name              = string
      freeform_tags             = map(string)
      id                        = string
      instance_configuration_id = string
      load_balancers = list(object(
        {
          backend_set_name = string
          id               = string
          instance_pool_id = string
          load_balancer_id = string
          port             = number
          state            = string
          vnic_selection   = string
        }
      ))
      placement_configurations = list(object(
        {
          availability_domain = string
          fault_domains       = list(string)
          primary_subnet_id   = string
          secondary_vnic_subnets = list(object(
            {
              display_name = string
              subnet_id    = string
            }
          ))
        }
      ))
      size         = number
      state        = string
      time_created = string
    }
  ))
}

variable "placement_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      availability_domain = string
      primary_subnet_id   = string
      secondary_vnic_subnets = set(object(
        {
          display_name = string
          subnet_id    = string
        }
      ))
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
resource "oci_core_cluster_network" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags

  dynamic "instance_pools" {
    for_each = var.instance_pools
    content {
      defined_tags              = instance_pools.value["defined_tags"]
      display_name              = instance_pools.value["display_name"]
      freeform_tags             = instance_pools.value["freeform_tags"]
      instance_configuration_id = instance_pools.value["instance_configuration_id"]
      size                      = instance_pools.value["size"]
    }
  }

  dynamic "placement_configuration" {
    for_each = var.placement_configuration
    content {
      availability_domain = placement_configuration.value["availability_domain"]
      primary_subnet_id   = placement_configuration.value["primary_subnet_id"]

      dynamic "secondary_vnic_subnets" {
        for_each = placement_configuration.value.secondary_vnic_subnets
        content {
          display_name = secondary_vnic_subnets.value["display_name"]
          subnet_id    = secondary_vnic_subnets.value["subnet_id"]
        }
      }

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
  value       = oci_core_cluster_network.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_cluster_network.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_cluster_network.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_cluster_network.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_cluster_network.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_cluster_network.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_core_cluster_network.this.time_updated
}

output "this" {
  value = oci_core_cluster_network.this
}
```

[top](#index)