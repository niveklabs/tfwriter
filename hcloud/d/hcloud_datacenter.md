# hcloud_datacenter

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
module "hcloud_datacenter" {
  source = "./modules/hcloud/d/hcloud_datacenter"

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
data "hcloud_datacenter" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "available_server_type_ids" {
  description = "returns a list of number"
  value       = data.hcloud_datacenter.this.available_server_type_ids
}

output "description" {
  description = "returns a string"
  value       = data.hcloud_datacenter.this.description
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_datacenter.this.id
}

output "location" {
  description = "returns a map of string"
  value       = data.hcloud_datacenter.this.location
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_datacenter.this.name
}

output "supported_server_type_ids" {
  description = "returns a list of number"
  value       = data.hcloud_datacenter.this.supported_server_type_ids
}

output "this" {
  value = hcloud_datacenter.this
}
```

[top](#index)