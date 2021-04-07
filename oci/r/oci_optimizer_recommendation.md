# oci_optimizer_recommendation

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
module "oci_optimizer_recommendation" {
  source = "./modules/oci/r/oci_optimizer_recommendation"

  # recommendation_id - (required) is a type of string
  recommendation_id = null
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
variable "recommendation_id" {
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
resource "oci_optimizer_recommendation" "this" {
  # recommendation_id - (required) is a type of string
  recommendation_id = var.recommendation_id
  # status - (required) is a type of string
  status = var.status
  # time_status_end - (optional) is a type of string
  time_status_end = var.time_status_end

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
output "category_id" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.category_id
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.description
}

output "estimated_cost_saving" {
  description = "returns a number"
  value       = oci_optimizer_recommendation.this.estimated_cost_saving
}

output "id" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.id
}

output "importance" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.importance
}

output "name" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.name
}

output "resource_counts" {
  description = "returns a list of object"
  value       = oci_optimizer_recommendation.this.resource_counts
}

output "state" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.state
}

output "supported_levels" {
  description = "returns a list of object"
  value       = oci_optimizer_recommendation.this.supported_levels
}

output "time_created" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.time_created
}

output "time_status_begin" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.time_status_begin
}

output "time_status_end" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.time_status_end
}

output "time_updated" {
  description = "returns a string"
  value       = oci_optimizer_recommendation.this.time_updated
}

output "this" {
  value = oci_optimizer_recommendation.this
}
```

[top](#index)