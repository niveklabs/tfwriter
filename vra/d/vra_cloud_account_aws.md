# vra_cloud_account_aws

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
module "vra_cloud_account_aws" {
  source = "./modules/vra/d/vra_cloud_account_aws"

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
data "vra_cloud_account_aws" "this" {
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
output "access_key" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.access_key
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_cloud_account_aws.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.owner
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_cloud_account_aws.this.regions
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_cloud_account_aws.this.updated_at
}

output "this" {
  value = vra_cloud_account_aws.this
}
```

[top](#index)