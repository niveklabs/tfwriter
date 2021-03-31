# hcloud_network

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "hcloud_network" {
  source = "./modules/hcloud/r/hcloud_network"

  # ip_range - (required) is a type of string
  ip_range = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_range" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_network" "this" {
  ip_range = var.ip_range
  labels   = var.labels
  name     = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_network.this.id
}

output "this" {
  value = hcloud_network.this
}
```

[top](#index)