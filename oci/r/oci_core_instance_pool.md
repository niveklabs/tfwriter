# oci_core_instance_pool

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
module "oci_core_instance_pool" {
  source = "./modules/oci/r/oci_core_instance_pool"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # instance_configuration_id - (required) is a type of string
  instance_configuration_id = null
  # size - (required) is a type of number
  size = null
  # state - (optional) is a type of string
  state = null

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

variable "instance_configuration_id" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}

variable "placement_configurations" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
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
resource "oci_core_instance_pool" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # instance_configuration_id - (required) is a type of string
  instance_configuration_id = var.instance_configuration_id
  # size - (required) is a type of number
  size = var.size
  # state - (optional) is a type of string
  state = var.state

  dynamic "load_balancers" {
    for_each = var.load_balancers
    content {
      # backend_set_name - (required) is a type of string
      backend_set_name = load_balancers.value["backend_set_name"]
      # load_balancer_id - (required) is a type of string
      load_balancer_id = load_balancers.value["load_balancer_id"]
      # port - (required) is a type of number
      port = load_balancers.value["port"]
      # vnic_selection - (required) is a type of string
      vnic_selection = load_balancers.value["vnic_selection"]
    }
  }

  dynamic "placement_configurations" {
    for_each = var.placement_configurations
    content {
      # availability_domain - (required) is a type of string
      availability_domain = placement_configurations.value["availability_domain"]
      # fault_domains - (optional) is a type of list of string
      fault_domains = placement_configurations.value["fault_domains"]
      # primary_subnet_id - (required) is a type of string
      primary_subnet_id = placement_configurations.value["primary_subnet_id"]

      dynamic "secondary_vnic_subnets" {
        for_each = placement_configurations.value.secondary_vnic_subnets
        content {
          # display_name - (optional) is a type of string
          display_name = secondary_vnic_subnets.value["display_name"]
          # subnet_id - (required) is a type of string
          subnet_id = secondary_vnic_subnets.value["subnet_id"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "actual_size" {
  description = "returns a number"
  value       = oci_core_instance_pool.this.actual_size
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_instance_pool.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_instance_pool.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_instance_pool.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_instance_pool.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_instance_pool.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_instance_pool.this.time_created
}

output "this" {
  value = oci_core_instance_pool.this
}
```

[top](#index)