# vra_cloud_account_gcp

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
module "vra_cloud_account_gcp" {
  source = "./modules/vra/d/vra_cloud_account_gcp"

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
data "vra_cloud_account_gcp" "this" {
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
output "client_email" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.client_email
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_cloud_account_gcp.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.owner
}

output "private_key_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.private_key_id
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.project_id
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_cloud_account_gcp.this.regions
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_gcp.this.updated_at
}

output "this" {
  value = vra_cloud_account_gcp.this
}
```

[top](#index)