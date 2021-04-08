# vra_block_device_snapshots

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
module "vra_block_device_snapshots" {
  source = "./modules/vra/d/vra_block_device_snapshots"

  # block_device_id - (required) is a type of string
  block_device_id = null
}
```

[top](#index)

### Variables

```terraform
variable "block_device_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_block_device_snapshots" "this" {
  # block_device_id - (required) is a type of string
  block_device_id = var.block_device_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vra_block_device_snapshots.this.id
}

output "snapshots" {
  description = "returns a list of object"
  value       = data.vra_block_device_snapshots.this.snapshots
}

output "this" {
  value = vra_block_device_snapshots.this
}
```

[top](#index)