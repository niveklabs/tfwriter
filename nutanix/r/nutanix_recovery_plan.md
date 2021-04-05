# nutanix_recovery_plan

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_recovery_plan" {
  source = "./modules/nutanix/r/nutanix_recovery_plan"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  categories = [{
    name  = null
    value = null
  }]

  owner_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  parameters = [{
    floating_ip_assignment_list = [{
      availability_zone_url = null
      vm_ip_assignment_list = [{
        recovery_floating_ip_config = [{
          ip                          = null
          should_allocate_dynamically = null
        }]
        test_floating_ip_config = [{
          ip                          = null
          should_allocate_dynamically = null
        }]
        vm_nic_information = [{
          ip   = null
          uuid = null
        }]
        vm_reference = [{
          kind = null
          name = null
          uuid = null
        }]
      }]
    }]
    network_mapping_list = [{
      are_networks_stretched = null
      availability_zone_network_mapping_list = [{
        availability_zone_url = null
        cluster_reference_list = [{
          kind = null
          name = null
          uuid = null
        }]
        recovery_ip_assignment_list = [{
          ip_config_list = [{
            ip_address = null
          }]
          vm_reference = [{
            kind = null
            name = null
            uuid = null
          }]
        }]
        recovery_network = [{
          name = null
          subnet_list = [{
            external_connectivity_state = null
            gateway_ip                  = null
            prefix_length               = null
          }]
          use_vpc_reference = null
          virtual_network_reference = [{
            kind = null
            name = null
            uuid = null
          }]
          vpc_reference = [{
            kind = null
            name = null
            uuid = null
          }]
        }]
        test_ip_assignment_list = [{
          ip_config_list = [{
            ip_address = null
          }]
          vm_reference = [{
            kind = null
            name = null
            uuid = null
          }]
        }]
        test_network = [{
          name = null
          subnet_list = [{
            external_connectivity_state = null
            gateway_ip                  = null
            prefix_length               = null
          }]
          use_vpc_reference = null
          virtual_network_reference = [{
            kind = null
            name = null
            uuid = null
          }]
          vpc_reference = [{
            kind = null
            name = null
            uuid = null
          }]
        }]
      }]
    }]
  }]

  project_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  stage_list = [{
    delay_time_secs = null
    stage_uuid      = null
    stage_work = [{
      recover_entities = [{
        entity_info_list = [{
          any_entity_reference_kind = null
          any_entity_reference_name = null
          any_entity_reference_uuid = null
          categories = [{
            name  = null
            value = null
          }]
          script_list = [{
            enable_script_exec = null
            timeout            = null
          }]
        }]
      }]
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "owner_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "parameters" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      floating_ip_assignment_list = list(object(
        {
          availability_zone_url = string
          vm_ip_assignment_list = list(object(
            {
              recovery_floating_ip_config = list(object(
                {
                  ip                          = string
                  should_allocate_dynamically = bool
                }
              ))
              test_floating_ip_config = list(object(
                {
                  ip                          = string
                  should_allocate_dynamically = bool
                }
              ))
              vm_nic_information = list(object(
                {
                  ip   = string
                  uuid = string
                }
              ))
              vm_reference = list(object(
                {
                  kind = string
                  name = string
                  uuid = string
                }
              ))
            }
          ))
        }
      ))
      network_mapping_list = list(object(
        {
          are_networks_stretched = bool
          availability_zone_network_mapping_list = list(object(
            {
              availability_zone_url = string
              cluster_reference_list = set(object(
                {
                  kind = string
                  name = string
                  uuid = string
                }
              ))
              recovery_ip_assignment_list = list(object(
                {
                  ip_config_list = list(object(
                    {
                      ip_address = string
                    }
                  ))
                  vm_reference = list(object(
                    {
                      kind = string
                      name = string
                      uuid = string
                    }
                  ))
                }
              ))
              recovery_network = list(object(
                {
                  name = string
                  subnet_list = list(object(
                    {
                      external_connectivity_state = string
                      gateway_ip                  = string
                      prefix_length               = number
                    }
                  ))
                  use_vpc_reference = bool
                  virtual_network_reference = list(object(
                    {
                      kind = string
                      name = string
                      uuid = string
                    }
                  ))
                  vpc_reference = list(object(
                    {
                      kind = string
                      name = string
                      uuid = string
                    }
                  ))
                }
              ))
              test_ip_assignment_list = list(object(
                {
                  ip_config_list = list(object(
                    {
                      ip_address = string
                    }
                  ))
                  vm_reference = list(object(
                    {
                      kind = string
                      name = string
                      uuid = string
                    }
                  ))
                }
              ))
              test_network = list(object(
                {
                  name = string
                  subnet_list = list(object(
                    {
                      external_connectivity_state = string
                      gateway_ip                  = string
                      prefix_length               = number
                    }
                  ))
                  use_vpc_reference = bool
                  virtual_network_reference = list(object(
                    {
                      kind = string
                      name = string
                      uuid = string
                    }
                  ))
                  vpc_reference = list(object(
                    {
                      kind = string
                      name = string
                      uuid = string
                    }
                  ))
                }
              ))
            }
          ))
        }
      ))
    }
  ))
}

variable "project_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "stage_list" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      delay_time_secs = number
      stage_uuid      = string
      stage_work = list(object(
        {
          recover_entities = list(object(
            {
              entity_info_list = list(object(
                {
                  any_entity_reference_kind = string
                  any_entity_reference_name = string
                  any_entity_reference_uuid = string
                  categories = set(object(
                    {
                      name  = string
                      value = string
                    }
                  ))
                  script_list = list(object(
                    {
                      enable_script_exec = bool
                      timeout            = string
                    }
                  ))
                }
              ))
            }
          ))
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_recovery_plan" "this" {
  description = var.description
  name        = var.name

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

  dynamic "owner_reference" {
    for_each = var.owner_reference
    content {
      kind = owner_reference.value["kind"]
      name = owner_reference.value["name"]
      uuid = owner_reference.value["uuid"]
    }
  }

  dynamic "parameters" {
    for_each = var.parameters
    content {

      dynamic "floating_ip_assignment_list" {
        for_each = parameters.value.floating_ip_assignment_list
        content {
          availability_zone_url = floating_ip_assignment_list.value["availability_zone_url"]

          dynamic "vm_ip_assignment_list" {
            for_each = floating_ip_assignment_list.value.vm_ip_assignment_list
            content {

              dynamic "recovery_floating_ip_config" {
                for_each = vm_ip_assignment_list.value.recovery_floating_ip_config
                content {
                  ip                          = recovery_floating_ip_config.value["ip"]
                  should_allocate_dynamically = recovery_floating_ip_config.value["should_allocate_dynamically"]
                }
              }

              dynamic "test_floating_ip_config" {
                for_each = vm_ip_assignment_list.value.test_floating_ip_config
                content {
                  ip                          = test_floating_ip_config.value["ip"]
                  should_allocate_dynamically = test_floating_ip_config.value["should_allocate_dynamically"]
                }
              }

              dynamic "vm_nic_information" {
                for_each = vm_ip_assignment_list.value.vm_nic_information
                content {
                  ip   = vm_nic_information.value["ip"]
                  uuid = vm_nic_information.value["uuid"]
                }
              }

              dynamic "vm_reference" {
                for_each = vm_ip_assignment_list.value.vm_reference
                content {
                  kind = vm_reference.value["kind"]
                  name = vm_reference.value["name"]
                  uuid = vm_reference.value["uuid"]
                }
              }

            }
          }

        }
      }

      dynamic "network_mapping_list" {
        for_each = parameters.value.network_mapping_list
        content {
          are_networks_stretched = network_mapping_list.value["are_networks_stretched"]

          dynamic "availability_zone_network_mapping_list" {
            for_each = network_mapping_list.value.availability_zone_network_mapping_list
            content {
              availability_zone_url = availability_zone_network_mapping_list.value["availability_zone_url"]

              dynamic "cluster_reference_list" {
                for_each = availability_zone_network_mapping_list.value.cluster_reference_list
                content {
                  kind = cluster_reference_list.value["kind"]
                  name = cluster_reference_list.value["name"]
                  uuid = cluster_reference_list.value["uuid"]
                }
              }

              dynamic "recovery_ip_assignment_list" {
                for_each = availability_zone_network_mapping_list.value.recovery_ip_assignment_list
                content {

                  dynamic "ip_config_list" {
                    for_each = recovery_ip_assignment_list.value.ip_config_list
                    content {
                      ip_address = ip_config_list.value["ip_address"]
                    }
                  }

                  dynamic "vm_reference" {
                    for_each = recovery_ip_assignment_list.value.vm_reference
                    content {
                      kind = vm_reference.value["kind"]
                      name = vm_reference.value["name"]
                      uuid = vm_reference.value["uuid"]
                    }
                  }

                }
              }

              dynamic "recovery_network" {
                for_each = availability_zone_network_mapping_list.value.recovery_network
                content {
                  name              = recovery_network.value["name"]
                  use_vpc_reference = recovery_network.value["use_vpc_reference"]

                  dynamic "subnet_list" {
                    for_each = recovery_network.value.subnet_list
                    content {
                      external_connectivity_state = subnet_list.value["external_connectivity_state"]
                      gateway_ip                  = subnet_list.value["gateway_ip"]
                      prefix_length               = subnet_list.value["prefix_length"]
                    }
                  }

                  dynamic "virtual_network_reference" {
                    for_each = recovery_network.value.virtual_network_reference
                    content {
                      kind = virtual_network_reference.value["kind"]
                      name = virtual_network_reference.value["name"]
                      uuid = virtual_network_reference.value["uuid"]
                    }
                  }

                  dynamic "vpc_reference" {
                    for_each = recovery_network.value.vpc_reference
                    content {
                      kind = vpc_reference.value["kind"]
                      name = vpc_reference.value["name"]
                      uuid = vpc_reference.value["uuid"]
                    }
                  }

                }
              }

              dynamic "test_ip_assignment_list" {
                for_each = availability_zone_network_mapping_list.value.test_ip_assignment_list
                content {

                  dynamic "ip_config_list" {
                    for_each = test_ip_assignment_list.value.ip_config_list
                    content {
                      ip_address = ip_config_list.value["ip_address"]
                    }
                  }

                  dynamic "vm_reference" {
                    for_each = test_ip_assignment_list.value.vm_reference
                    content {
                      kind = vm_reference.value["kind"]
                      name = vm_reference.value["name"]
                      uuid = vm_reference.value["uuid"]
                    }
                  }

                }
              }

              dynamic "test_network" {
                for_each = availability_zone_network_mapping_list.value.test_network
                content {
                  name              = test_network.value["name"]
                  use_vpc_reference = test_network.value["use_vpc_reference"]

                  dynamic "subnet_list" {
                    for_each = test_network.value.subnet_list
                    content {
                      external_connectivity_state = subnet_list.value["external_connectivity_state"]
                      gateway_ip                  = subnet_list.value["gateway_ip"]
                      prefix_length               = subnet_list.value["prefix_length"]
                    }
                  }

                  dynamic "virtual_network_reference" {
                    for_each = test_network.value.virtual_network_reference
                    content {
                      kind = virtual_network_reference.value["kind"]
                      name = virtual_network_reference.value["name"]
                      uuid = virtual_network_reference.value["uuid"]
                    }
                  }

                  dynamic "vpc_reference" {
                    for_each = test_network.value.vpc_reference
                    content {
                      kind = vpc_reference.value["kind"]
                      name = vpc_reference.value["name"]
                      uuid = vpc_reference.value["uuid"]
                    }
                  }

                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "project_reference" {
    for_each = var.project_reference
    content {
      kind = project_reference.value["kind"]
      name = project_reference.value["name"]
      uuid = project_reference.value["uuid"]
    }
  }

  dynamic "stage_list" {
    for_each = var.stage_list
    content {
      delay_time_secs = stage_list.value["delay_time_secs"]
      stage_uuid      = stage_list.value["stage_uuid"]

      dynamic "stage_work" {
        for_each = stage_list.value.stage_work
        content {

          dynamic "recover_entities" {
            for_each = stage_work.value.recover_entities
            content {

              dynamic "entity_info_list" {
                for_each = recover_entities.value.entity_info_list
                content {
                  any_entity_reference_kind = entity_info_list.value["any_entity_reference_kind"]
                  any_entity_reference_name = entity_info_list.value["any_entity_reference_name"]
                  any_entity_reference_uuid = entity_info_list.value["any_entity_reference_uuid"]

                  dynamic "categories" {
                    for_each = entity_info_list.value.categories
                    content {
                      name  = categories.value["name"]
                      value = categories.value["value"]
                    }
                  }

                  dynamic "script_list" {
                    for_each = entity_info_list.value.script_list
                    content {
                      enable_script_exec = script_list.value["enable_script_exec"]
                      timeout            = script_list.value["timeout"]
                    }
                  }

                }
              }

            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_recovery_plan.this.api_version
}

output "description" {
  description = "returns a string"
  value       = nutanix_recovery_plan.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_recovery_plan.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_recovery_plan.this.metadata
}

output "state" {
  description = "returns a string"
  value       = nutanix_recovery_plan.this.state
}

output "this" {
  value = nutanix_recovery_plan.this
}
```

[top](#index)