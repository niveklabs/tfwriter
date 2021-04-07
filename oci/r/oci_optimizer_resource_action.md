# oci_optimizer_resource_action

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
module "oci_optimizer_resource_action" {
  source = "./modules/oci/r/oci_optimizer_resource_action"

  # resource_action_id - (required) is a type of string
  resource_action_id = null
  # status - (required) is a type of string
  status = null
  # time_status_end - (optional) is a type of string
  time_status_end = null

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
variable "resource_action_id" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "time_status_end" {
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
resource "oci_optimizer_resource_action" "this" {
  resource_action_id = var.resource_action_id
  status             = var.status
  time_status_end    = var.time_status_end

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
output "action" {
  description = "returns a list of object"
  value       = oci_optimizer_resource_action.this.action
}

output "category_id" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.category_id
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.compartment_id
}

output "compartment_name" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.compartment_name
}

output "estimated_cost_saving" {
  description = "returns a number"
  value       = oci_optimizer_resource_action.this.estimated_cost_saving
}

output "extended_metadata" {
  description = "returns a map of string"
  value       = oci_optimizer_resource_action.this.extended_metadata
}

output "id" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = oci_optimizer_resource_action.this.metadata
}

output "name" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.name
}

output "recommendation_id" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.recommendation_id
}

output "resource_id" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.resource_id
}

output "resource_type" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.resource_type
}

output "state" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.time_created
}

output "time_status_begin" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.time_status_begin
}

output "time_status_end" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.time_status_end
}

output "time_updated" {
  description = "returns a string"
  value       = oci_optimizer_resource_action.this.time_updated
}

output "this" {
  value = oci_optimizer_resource_action.this
}
```

[top](#index)