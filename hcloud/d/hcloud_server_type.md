# hcloud_server_type

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_server_type" {
  source = "./modules/hcloud/d/hcloud_server_type"

  # name - (optional) is a type of string
  name = null
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
```

[top](#index)

### Datasource

```terraform
data "hcloud_server_type" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cores" {
  description = "returns a number"
  value       = data.hcloud_server_type.this.cores
}

output "cpu_type" {
  description = "returns a string"
  value       = data.hcloud_server_type.this.cpu_type
}

output "description" {
  description = "returns a string"
  value       = data.hcloud_server_type.this.description
}

output "disk" {
  description = "returns a number"
  value       = data.hcloud_server_type.this.disk
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_server_type.this.id
}

output "memory" {
  description = "returns a number"
  value       = data.hcloud_server_type.this.memory
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_server_type.this.name
}

output "storage_type" {
  description = "returns a string"
  value       = data.hcloud_server_type.this.storage_type
}

output "this" {
  value = hcloud_server_type.this
}
```

[top](#index)