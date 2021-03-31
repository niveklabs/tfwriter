# oci_optimizer_recommendation

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_optimizer_recommendation" {
  source = "./modules/oci/d/oci_optimizer_recommendation"

  # recommendation_id - (required) is a type of string
  recommendation_id = null
}
```

[top](#index)

### Variables

```terraform
variable "recommendation_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_optimizer_recommendation" "this" {
  recommendation_id = var.recommendation_id
}
```

[top](#index)

### Outputs

```terraform
output "category_id" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.category_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.description
}

output "estimated_cost_saving" {
  description = "returns a number"
  value       = data.oci_optimizer_recommendation.this.estimated_cost_saving
}

output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.id
}

output "importance" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.importance
}

output "name" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.name
}

output "resource_counts" {
  description = "returns a list of object"
  value       = data.oci_optimizer_recommendation.this.resource_counts
}

output "state" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.state
}

output "status" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.status
}

output "supported_levels" {
  description = "returns a list of object"
  value       = data.oci_optimizer_recommendation.this.supported_levels
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.time_created
}

output "time_status_begin" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.time_status_begin
}

output "time_status_end" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.time_status_end
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation.this.time_updated
}

output "this" {
  value = oci_optimizer_recommendation.this
}
```

[top](#index)