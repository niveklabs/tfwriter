# hcloud_snapshot

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
module "hcloud_snapshot" {
  source = "./modules/hcloud/r/hcloud_snapshot"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # server_id - (required) is a type of number
  server_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_snapshot" "this" {
  description = var.description
  labels      = var.labels
  server_id   = var.server_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_snapshot.this.id
}

output "this" {
  value = hcloud_snapshot.this
}
```

[top](#index)