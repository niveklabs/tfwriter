# vra_cloud_account_azure

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
module "vra_cloud_account_azure" {
  source = "./modules/vra/d/vra_cloud_account_azure"

  # name - (optional) is a type of string
  name = null

  tags = [{
    key   = null
    value = null
  }]
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

### Datasource

```terraform
data "vra_cloud_account_azure" "this" {
  # name - (optional) is a type of string
  name = var.name

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
output "application_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.application_id
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_cloud_account_azure.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.owner
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_cloud_account_azure.this.regions
}

output "subscription_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.subscription_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_azure.this.tenant_id
}

output "this" {
  value = vra_cloud_account_azure.this
}
```

[top](#index)