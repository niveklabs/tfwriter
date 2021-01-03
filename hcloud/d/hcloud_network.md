# hcloud_network

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
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_network" {
  source = "./modules/hcloud/d/hcloud_network"

  # ip_range - (optional) is a type of string
  ip_range = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # with_selector - (optional) is a type of string
  with_selector = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_network" "this" {
  ip_range      = var.ip_range
  labels        = var.labels
  name          = var.name
  with_selector = var.with_selector
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a number"
  value       = data.hcloud_network.this.id
}

output "this" {
  value = hcloud_network.this
}
```

[top](#index)