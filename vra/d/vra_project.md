# vra_project

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_project" {
  source = "./modules/vra/d/vra_project"

  # administrators - (optional) is a type of set of string
  administrators = []
  # description - (optional) is a type of string
  description = null
  # machine_naming_template - (optional) is a type of string
  machine_naming_template = null
  # members - (optional) is a type of set of string
  members = []
  # name - (optional) is a type of string
  name = null
  # operation_timeout - (optional) is a type of number
  operation_timeout = null
  # shared_resources - (optional) is a type of bool
  shared_resources = null
  # viewers - (optional) is a type of set of string
  viewers = []

  constraints = [{
    extensibility = [{
      expression = null
      mandatory  = null
    }]
    network = [{
      expression = null
      mandatory  = null
    }]
    storage = [{
      expression = null
      mandatory  = null
    }]
  }]

  zone_assignments = [{
    cpu_limit        = null
    max_instances    = null
    memory_limit_mb  = null
    priority         = null
    storage_limit_gb = null
    zone_id          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "administrators" {
  description = "(optional) - List of administrator users associated with the project. Only administrators can manage project's configuration."
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "machine_naming_template" {
  description = "(optional) - The naming template to be used for resources provisioned in this project."
  type        = string
  default     = null
}

variable "members" {
  description = "(optional) - List of member users associated with the project."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - A human-friendly name used as an identifier in APIs that support this option."
  type        = string
  default     = null
}

variable "operation_timeout" {
  description = "(optional) - The timeout that should be used for Blueprint operations and Provisioning tasks. The timeout is in seconds."
  type        = number
  default     = null
}

variable "shared_resources" {
  description = "(optional) - Specifies whether the resources in this projects are shared or not. If not set default will be used."
  type        = bool
  default     = null
}

variable "viewers" {
  description = "(optional) - List of viewer users associated with the project."
  type        = set(string)
  default     = null
}

variable "constraints" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      extensibility = set(object(
        {
          expression = string
          mandatory  = bool
        }
      ))
      network = set(object(
        {
          expression = string
          mandatory  = bool
        }
      ))
      storage = set(object(
        {
          expression = string
          mandatory  = bool
        }
      ))
    }
  ))
  default = []
}

variable "zone_assignments" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cpu_limit        = number
      max_instances    = number
      memory_limit_mb  = number
      priority         = number
      storage_limit_gb = number
      zone_id          = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vra_project" "this" {
  # administrators - (optional) is a type of set of string
  administrators = var.administrators
  # description - (optional) is a type of string
  description = var.description
  # machine_naming_template - (optional) is a type of string
  machine_naming_template = var.machine_naming_template
  # members - (optional) is a type of set of string
  members = var.members
  # name - (optional) is a type of string
  name = var.name
  # operation_timeout - (optional) is a type of number
  operation_timeout = var.operation_timeout
  # shared_resources - (optional) is a type of bool
  shared_resources = var.shared_resources
  # viewers - (optional) is a type of set of string
  viewers = var.viewers

  dynamic "constraints" {
    for_each = var.constraints
    content {

      dynamic "extensibility" {
        for_each = constraints.value.extensibility
        content {
          # expression - (required) is a type of string
          expression = extensibility.value["expression"]
          # mandatory - (required) is a type of bool
          mandatory = extensibility.value["mandatory"]
        }
      }

      dynamic "network" {
        for_each = constraints.value.network
        content {
          # expression - (required) is a type of string
          expression = network.value["expression"]
          # mandatory - (required) is a type of bool
          mandatory = network.value["mandatory"]
        }
      }

      dynamic "storage" {
        for_each = constraints.value.storage
        content {
          # expression - (required) is a type of string
          expression = storage.value["expression"]
          # mandatory - (required) is a type of bool
          mandatory = storage.value["mandatory"]
        }
      }

    }
  }

  dynamic "zone_assignments" {
    for_each = var.zone_assignments
    content {
      # cpu_limit - (optional) is a type of number
      cpu_limit = zone_assignments.value["cpu_limit"]
      # max_instances - (optional) is a type of number
      max_instances = zone_assignments.value["max_instances"]
      # memory_limit_mb - (optional) is a type of number
      memory_limit_mb = zone_assignments.value["memory_limit_mb"]
      # priority - (optional) is a type of number
      priority = zone_assignments.value["priority"]
      # storage_limit_gb - (optional) is a type of number
      storage_limit_gb = zone_assignments.value["storage_limit_gb"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "administrators" {
  description = "returns a set of string"
  value       = data.vra_project.this.administrators
}

output "description" {
  description = "returns a string"
  value       = data.vra_project.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_project.this.id
}

output "members" {
  description = "returns a set of string"
  value       = data.vra_project.this.members
}

output "name" {
  description = "returns a string"
  value       = data.vra_project.this.name
}

output "shared_resources" {
  description = "returns a bool"
  value       = data.vra_project.this.shared_resources
}

output "viewers" {
  description = "returns a set of string"
  value       = data.vra_project.this.viewers
}

output "this" {
  value = vra_project.this
}
```

[top](#index)