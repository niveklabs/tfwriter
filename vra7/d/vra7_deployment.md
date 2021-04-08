# vra7_deployment

[back](../vra7.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra7 = ">= 3.0.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra7_deployment" {
  source = "./modules/vra7/d/vra7_deployment"

  # deployment_id - (optional) is a type of string
  deployment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vra7_deployment" "this" {
  # deployment_id - (optional) is a type of string
  deployment_id = var.deployment_id
}
```

[top](#index)

### Outputs

```terraform
output "businessgroup_id" {
  description = "returns a string"
  value       = data.vra7_deployment.this.businessgroup_id
}

output "businessgroup_name" {
  description = "returns a string"
  value       = data.vra7_deployment.this.businessgroup_name
}

output "catalog_item_id" {
  description = "returns a string"
  value       = data.vra7_deployment.this.catalog_item_id
}

output "catalog_item_name" {
  description = "returns a string"
  value       = data.vra7_deployment.this.catalog_item_name
}

output "created_date" {
  description = "returns a string"
  value       = data.vra7_deployment.this.created_date
}

output "deployment_id" {
  description = "returns a string"
  value       = data.vra7_deployment.this.deployment_id
}

output "description" {
  description = "returns a string"
  value       = data.vra7_deployment.this.description
}

output "expiry_date" {
  description = "returns a string"
  value       = data.vra7_deployment.this.expiry_date
}

output "id" {
  description = "returns a string"
  value       = data.vra7_deployment.this.id
}

output "lease_days" {
  description = "returns a number"
  value       = data.vra7_deployment.this.lease_days
}

output "name" {
  description = "returns a string"
  value       = data.vra7_deployment.this.name
}

output "owners" {
  description = "returns a set of object"
  value       = data.vra7_deployment.this.owners
}

output "reasons" {
  description = "returns a string"
  value       = data.vra7_deployment.this.reasons
}

output "request_status" {
  description = "returns a string"
  value       = data.vra7_deployment.this.request_status
}

output "resource_configuration" {
  description = "returns a set of object"
  value       = data.vra7_deployment.this.resource_configuration
}

output "this" {
  value = vra7_deployment.this
}
```

[top](#index)