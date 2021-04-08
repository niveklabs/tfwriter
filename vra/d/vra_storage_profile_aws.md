# vra_storage_profile_aws

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
module "vra_storage_profile_aws" {
  source = "./modules/vra/d/vra_storage_profile_aws"

  # filter - (optional) is a type of string
  filter = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
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
data "vra_storage_profile_aws" "this" {
  # filter - (optional) is a type of string
  filter = var.filter

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
output "cloud_account_id" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.created_at
}

output "default_item" {
  description = "returns a bool"
  value       = data.vra_storage_profile_aws.this.default_item
}

output "description" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.description
}

output "device_type" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.device_type
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.id
}

output "iops" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.iops
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_storage_profile_aws.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.owner
}

output "supports_encryption" {
  description = "returns a bool"
  value       = data.vra_storage_profile_aws.this.supports_encryption
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.updated_at
}

output "volume_type" {
  description = "returns a string"
  value       = data.vra_storage_profile_aws.this.volume_type
}

output "this" {
  value = vra_storage_profile_aws.this
}
```

[top](#index)