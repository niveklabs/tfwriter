# hcloud_ssh_key

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
module "hcloud_ssh_key" {
  source = "./modules/hcloud/r/hcloud_ssh_key"

  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # public_key - (required) is a type of string
  public_key = null
}
```

[top](#index)

### Variables

```terraform
variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_ssh_key" "this" {
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # public_key - (required) is a type of string
  public_key = var.public_key
}
```

[top](#index)

### Outputs

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = hcloud_ssh_key.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = hcloud_ssh_key.this.id
}

output "this" {
  value = hcloud_ssh_key.this
}
```

[top](#index)