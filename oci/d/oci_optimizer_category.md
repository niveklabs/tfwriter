# oci_optimizer_category

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
module "oci_optimizer_category" {
  source = "./modules/oci/d/oci_optimizer_category"

  # category_id - (required) is a type of string
  category_id = null
}
```

[top](#index)

### Variables

```terraform
variable "category_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_optimizer_category" "this" {
  category_id = var.category_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.description
}

output "estimated_cost_saving" {
  description = "returns a number"
  value       = data.oci_optimizer_category.this.estimated_cost_saving
}

output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.name
}

output "recommendation_counts" {
  description = "returns a list of object"
  value       = data.oci_optimizer_category.this.recommendation_counts
}

output "resource_counts" {
  description = "returns a list of object"
  value       = data.oci_optimizer_category.this.resource_counts
}

output "state" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_optimizer_category.this.time_updated
}

output "this" {
  value = oci_optimizer_category.this
}
```

[top](#index)