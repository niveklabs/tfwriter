# hcloud_volume_attachment

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
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_volume_attachment" {
  source = "./modules/hcloud/r/hcloud_volume_attachment"

  # automount - (optional) is a type of bool
  automount = null
  # server_id - (required) is a type of number
  server_id = null
  # volume_id - (required) is a type of number
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "automount" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = number
}

variable "volume_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_volume_attachment" "this" {
  automount = var.automount
  server_id = var.server_id
  volume_id = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "automount" {
  description = "returns a bool"
  value       = hcloud_volume_attachment.this.automount
}

output "id" {
  description = "returns a string"
  value       = hcloud_volume_attachment.this.id
}

output "this" {
  value = hcloud_volume_attachment.this
}
```

[top](#index)