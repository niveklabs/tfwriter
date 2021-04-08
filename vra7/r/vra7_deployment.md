# vra7_deployment

[back](../vra7.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vra7/r/vra7_deployment"

  # businessgroup_id - (optional) is a type of string
  businessgroup_id = null
  # businessgroup_name - (optional) is a type of string
  businessgroup_name = null
  # catalog_item_id - (optional) is a type of string
  catalog_item_id = null
  # catalog_item_name - (optional) is a type of string
  catalog_item_name = null
  # deployment_configuration - (optional) is a type of map of string
  deployment_configuration = {}
  # deployment_destroy - (optional) is a type of bool
  deployment_destroy = null
  # description - (optional) is a type of string
  description = null
  # expiry_date - (optional) is a type of string
  expiry_date = null
  # lease_days - (optional) is a type of number
  lease_days = null
  # reasons - (optional) is a type of string
  reasons = null
  # wait_timeout - (optional) is a type of number
  wait_timeout = null

  resource_configuration = [{
    cluster        = null
    component_name = null
    configuration  = {}
    instances = [{
      description   = null
      ip_address    = null
      name          = null
      properties    = {}
      resource_id   = null
      resource_type = null
    }]
    parent_resource_id = null
    request_id         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "businessgroup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "businessgroup_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "catalog_item_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "catalog_item_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_configuration" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "deployment_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiry_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lease_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reasons" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cluster        = number
      component_name = string
      configuration  = map(string)
      instances = list(object(
        {
          description   = string
          ip_address    = string
          name          = string
          properties    = map(string)
          resource_id   = string
          resource_type = string
        }
      ))
      parent_resource_id = string
      request_id         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra7_deployment" "this" {
  # businessgroup_id - (optional) is a type of string
  businessgroup_id = var.businessgroup_id
  # businessgroup_name - (optional) is a type of string
  businessgroup_name = var.businessgroup_name
  # catalog_item_id - (optional) is a type of string
  catalog_item_id = var.catalog_item_id
  # catalog_item_name - (optional) is a type of string
  catalog_item_name = var.catalog_item_name
  # deployment_configuration - (optional) is a type of map of string
  deployment_configuration = var.deployment_configuration
  # deployment_destroy - (optional) is a type of bool
  deployment_destroy = var.deployment_destroy
  # description - (optional) is a type of string
  description = var.description
  # expiry_date - (optional) is a type of string
  expiry_date = var.expiry_date
  # lease_days - (optional) is a type of number
  lease_days = var.lease_days
  # reasons - (optional) is a type of string
  reasons = var.reasons
  # wait_timeout - (optional) is a type of number
  wait_timeout = var.wait_timeout

  dynamic "resource_configuration" {
    for_each = var.resource_configuration
    content {
      # cluster - (optional) is a type of number
      cluster = resource_configuration.value["cluster"]
      # component_name - (required) is a type of string
      component_name = resource_configuration.value["component_name"]
      # configuration - (optional) is a type of map of string
      configuration = resource_configuration.value["configuration"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "businessgroup_id" {
  description = "returns a string"
  value       = vra7_deployment.this.businessgroup_id
}

output "businessgroup_name" {
  description = "returns a string"
  value       = vra7_deployment.this.businessgroup_name
}

output "catalog_item_id" {
  description = "returns a string"
  value       = vra7_deployment.this.catalog_item_id
}

output "created_date" {
  description = "returns a string"
  value       = vra7_deployment.this.created_date
}

output "deployment_id" {
  description = "returns a string"
  value       = vra7_deployment.this.deployment_id
}

output "description" {
  description = "returns a string"
  value       = vra7_deployment.this.description
}

output "expiry_date" {
  description = "returns a string"
  value       = vra7_deployment.this.expiry_date
}

output "id" {
  description = "returns a string"
  value       = vra7_deployment.this.id
}

output "lease_days" {
  description = "returns a number"
  value       = vra7_deployment.this.lease_days
}

output "name" {
  description = "returns a string"
  value       = vra7_deployment.this.name
}

output "owners" {
  description = "returns a list of object"
  value       = vra7_deployment.this.owners
}

output "request_status" {
  description = "returns a string"
  value       = vra7_deployment.this.request_status
}

output "this" {
  value = vra7_deployment.this
}
```

[top](#index)