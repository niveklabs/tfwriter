# avi_poolgroupdeploymentpolicy

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_poolgroupdeploymentpolicy" {
  source = "./modules/avi/d/avi_poolgroupdeploymentpolicy"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_poolgroupdeploymentpolicy" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "auto_disable_old_prod_pools" {
  description = "returns a bool"
  value       = data.avi_poolgroupdeploymentpolicy.this.auto_disable_old_prod_pools
}

output "description" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.description
}

output "evaluation_duration" {
  description = "returns a number"
  value       = data.avi_poolgroupdeploymentpolicy.this.evaluation_duration
}

output "id" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.name
}

output "rules" {
  description = "returns a list of object"
  value       = data.avi_poolgroupdeploymentpolicy.this.rules
}

output "scheme" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.scheme
}

output "target_test_traffic_ratio" {
  description = "returns a number"
  value       = data.avi_poolgroupdeploymentpolicy.this.target_test_traffic_ratio
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.tenant_ref
}

output "test_traffic_ratio_rampup" {
  description = "returns a number"
  value       = data.avi_poolgroupdeploymentpolicy.this.test_traffic_ratio_rampup
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.uuid
}

output "webhook_ref" {
  description = "returns a string"
  value       = data.avi_poolgroupdeploymentpolicy.this.webhook_ref
}

output "this" {
  value = avi_poolgroupdeploymentpolicy.this
}
```

[top](#index)