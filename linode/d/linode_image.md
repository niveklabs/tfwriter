# linode_image

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "linode_image" {
  source = "./modules/linode/d/linode_image"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "linode_image" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.linode_image.this.created
}

output "created_by" {
  description = "returns a string"
  value       = data.linode_image.this.created_by
}

output "deprecated" {
  description = "returns a bool"
  value       = data.linode_image.this.deprecated
}

output "description" {
  description = "returns a string"
  value       = data.linode_image.this.description
}

output "expiry" {
  description = "returns a string"
  value       = data.linode_image.this.expiry
}

output "id" {
  description = "returns a string"
  value       = data.linode_image.this.id
}

output "is_public" {
  description = "returns a bool"
  value       = data.linode_image.this.is_public
}

output "label" {
  description = "returns a string"
  value       = data.linode_image.this.label
}

output "size" {
  description = "returns a number"
  value       = data.linode_image.this.size
}

output "type" {
  description = "returns a string"
  value       = data.linode_image.this.type
}

output "vendor" {
  description = "returns a string"
  value       = data.linode_image.this.vendor
}

output "this" {
  value = linode_image.this
}
```

[top](#index)