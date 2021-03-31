# hcloud_ssh_key

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
module "hcloud_ssh_key" {
  source = "./modules/hcloud/d/hcloud_ssh_key"

  # fingerprint - (optional) is a type of string
  fingerprint = null
  # name - (optional) is a type of string
  name = null
  # selector - (optional) is a type of string
  selector = null
  # with_selector - (optional) is a type of string
  with_selector = null
}
```

[top](#index)

### Variables

```terraform
variable "fingerprint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector" {
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
data "hcloud_ssh_key" "this" {
  fingerprint   = var.fingerprint
  name          = var.name
  selector      = var.selector
  with_selector = var.with_selector
}
```

[top](#index)

### Outputs

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = data.hcloud_ssh_key.this.fingerprint
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_ssh_key.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_ssh_key.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_ssh_key.this.name
}

output "public_key" {
  description = "returns a string"
  value       = data.hcloud_ssh_key.this.public_key
}

output "this" {
  value = hcloud_ssh_key.this
}
```

[top](#index)