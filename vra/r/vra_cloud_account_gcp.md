# vra_cloud_account_gcp

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
module "vra_cloud_account_gcp" {
  source = "./modules/vra/r/vra_cloud_account_gcp"

  # client_email - (required) is a type of string
  client_email = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # private_key - (required) is a type of string
  private_key = null
  # private_key_id - (required) is a type of string
  private_key_id = null
  # project_id - (required) is a type of string
  project_id = null
  # regions - (optional) is a type of list of string
  regions = []

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "client_email" {
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

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "private_key_id" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "regions" {
  description = "(optional)"
  type        = list(string)
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

### Resource

```terraform
resource "vra_cloud_account_gcp" "this" {
  # client_email - (required) is a type of string
  client_email = var.client_email
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # private_key - (required) is a type of string
  private_key = var.private_key
  # private_key_id - (required) is a type of string
  private_key_id = var.private_key_id
  # project_id - (required) is a type of string
  project_id = var.project_id
  # regions - (optional) is a type of list of string
  regions = var.regions

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
  value       = vra_cloud_account_gcp.this.created_at
}

output "id" {
  description = "returns a string"
  value       = vra_cloud_account_gcp.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_cloud_account_gcp.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_cloud_account_gcp.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_cloud_account_gcp.this.owner
}

output "region_ids" {
  description = "returns a list of string"
  value       = vra_cloud_account_gcp.this.region_ids
}

output "updated_at" {
  description = "returns a string"
  value       = vra_cloud_account_gcp.this.updated_at
}

output "this" {
  value = vra_cloud_account_gcp.this
}
```

[top](#index)