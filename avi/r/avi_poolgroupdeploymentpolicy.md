# avi_poolgroupdeploymentpolicy

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/avi/r/avi_poolgroupdeploymentpolicy"

  # auto_disable_old_prod_pools - (optional) is a type of bool
  auto_disable_old_prod_pools = null
  # description - (optional) is a type of string
  description = null
  # evaluation_duration - (optional) is a type of number
  evaluation_duration = null
  # name - (required) is a type of string
  name = null
  # scheme - (optional) is a type of string
  scheme = null
  # target_test_traffic_ratio - (optional) is a type of number
  target_test_traffic_ratio = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # test_traffic_ratio_rampup - (optional) is a type of number
  test_traffic_ratio_rampup = null
  # uuid - (optional) is a type of string
  uuid = null
  # webhook_ref - (optional) is a type of string
  webhook_ref = null

  rules = [{
    metric_id = null
    operator  = null
    threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_disable_old_prod_pools" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "evaluation_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scheme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_test_traffic_ratio" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "test_traffic_ratio_rampup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webhook_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      metric_id = string
      operator  = string
      threshold = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_poolgroupdeploymentpolicy" "this" {
  # auto_disable_old_prod_pools - (optional) is a type of bool
  auto_disable_old_prod_pools = var.auto_disable_old_prod_pools
  # description - (optional) is a type of string
  description = var.description
  # evaluation_duration - (optional) is a type of number
  evaluation_duration = var.evaluation_duration
  # name - (required) is a type of string
  name = var.name
  # scheme - (optional) is a type of string
  scheme = var.scheme
  # target_test_traffic_ratio - (optional) is a type of number
  target_test_traffic_ratio = var.target_test_traffic_ratio
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # test_traffic_ratio_rampup - (optional) is a type of number
  test_traffic_ratio_rampup = var.test_traffic_ratio_rampup
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # webhook_ref - (optional) is a type of string
  webhook_ref = var.webhook_ref

  dynamic "rules" {
    for_each = var.rules
    content {
      # metric_id - (optional) is a type of string
      metric_id = rules.value["metric_id"]
      # operator - (optional) is a type of string
      operator = rules.value["operator"]
      # threshold - (optional) is a type of number
      threshold = rules.value["threshold"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_poolgroupdeploymentpolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_poolgroupdeploymentpolicy.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_poolgroupdeploymentpolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_poolgroupdeploymentpolicy.this.uuid
}

output "webhook_ref" {
  description = "returns a string"
  value       = avi_poolgroupdeploymentpolicy.this.webhook_ref
}

output "this" {
  value = avi_poolgroupdeploymentpolicy.this
}
```

[top](#index)