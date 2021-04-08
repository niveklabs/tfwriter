# vra_cloud_account_azure

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vra_cloud_account_azure" {
  source = "./modules/vra/r/vra_cloud_account_azure"

  # application_id - (required) is a type of string
  application_id = null
  # application_key - (required) is a type of string
  application_key = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # regions - (optional) is a type of list of string
  regions = []
  # subscription_id - (required) is a type of string
  subscription_id = null
  # tenant_id - (required) is a type of string
  tenant_id = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "application_key" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "regions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "subscription_id" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_cloud_account_azure" "this" {
  # application_id - (required) is a type of string
  application_id = var.application_id
  # application_key - (required) is a type of string
  application_key = var.application_key
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # regions - (optional) is a type of list of string
  regions = var.regions
  # subscription_id - (required) is a type of string
  subscription_id = var.subscription_id
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_cloud_account_azure.this.created_at
}

output "id" {
  description = "returns a string"
  value       = vra_cloud_account_azure.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_cloud_account_azure.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_cloud_account_azure.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_cloud_account_azure.this.owner
}

output "region_ids" {
  description = "returns a list of string"
  value       = vra_cloud_account_azure.this.region_ids
}

output "updated_at" {
  description = "returns a string"
  value       = vra_cloud_account_azure.this.updated_at
}

output "this" {
  value = vra_cloud_account_azure.this
}
```

[top](#index)