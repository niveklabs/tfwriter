# linode_object_storage_key

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_object_storage_key" {
  source = "./modules/linode/r/linode_object_storage_key"

  # label - (required) is a type of string
  label = null

  bucket_access = [{
    bucket_name = null
    cluster     = null
    permissions = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required) - The label given to this key. For display purposes only."
  type        = string
}

variable "bucket_access" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name = string
      cluster     = string
      permissions = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_object_storage_key" "this" {
  # label - (required) is a type of string
  label = var.label

  dynamic "bucket_access" {
    for_each = var.bucket_access
    content {
      # bucket_name - (required) is a type of string
      bucket_name = bucket_access.value["bucket_name"]
      # cluster - (required) is a type of string
      cluster = bucket_access.value["cluster"]
      # permissions - (required) is a type of string
      permissions = bucket_access.value["permissions"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_key" {
  description = "returns a string"
  value       = linode_object_storage_key.this.access_key
}

output "id" {
  description = "returns a string"
  value       = linode_object_storage_key.this.id
}

output "limited" {
  description = "returns a bool"
  value       = linode_object_storage_key.this.limited
}

output "secret_key" {
  description = "returns a string"
  value       = linode_object_storage_key.this.secret_key
  sensitive   = true
}

output "this" {
  value = linode_object_storage_key.this
}
```

[top](#index)