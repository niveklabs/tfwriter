# linode_volume

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
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_volume" {
  source = "./modules/linode/d/linode_volume"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "linode_volume" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.linode_volume.this.created
}

output "filesystem_path" {
  description = "returns a string"
  value       = data.linode_volume.this.filesystem_path
}

output "id" {
  description = "returns a number"
  value       = data.linode_volume.this.id
}

output "label" {
  description = "returns a string"
  value       = data.linode_volume.this.label
}

output "linode_id" {
  description = "returns a number"
  value       = data.linode_volume.this.linode_id
}

output "region" {
  description = "returns a string"
  value       = data.linode_volume.this.region
}

output "size" {
  description = "returns a number"
  value       = data.linode_volume.this.size
}

output "status" {
  description = "returns a string"
  value       = data.linode_volume.this.status
}

output "tags" {
  description = "returns a set of string"
  value       = data.linode_volume.this.tags
}

output "updated" {
  description = "returns a string"
  value       = data.linode_volume.this.updated
}

output "this" {
  value = linode_volume.this
}
```

[top](#index)