# hcloud_floating_ip_assignment

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
module "hcloud_floating_ip_assignment" {
  source = "./modules/hcloud/r/hcloud_floating_ip_assignment"

  # floating_ip_id - (required) is a type of number
  floating_ip_id = null
  # server_id - (required) is a type of number
  server_id = null
}
```

[top](#index)

### Variables

```terraform
variable "floating_ip_id" {
  description = "(required)"
  type        = number
}

variable "server_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_floating_ip_assignment" "this" {
  floating_ip_id = var.floating_ip_id
  server_id      = var.server_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_floating_ip_assignment.this.id
}

output "this" {
  value = hcloud_floating_ip_assignment.this
}
```

[top](#index)