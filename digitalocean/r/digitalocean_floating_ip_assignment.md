# digitalocean_floating_ip_assignment

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_floating_ip_assignment" {
  source = "./modules/digitalocean/r/digitalocean_floating_ip_assignment"

  # droplet_id - (required) is a type of number
  droplet_id = null
  # ip_address - (required) is a type of string
  ip_address = null
}
```

[top](#index)

### Variables

```terraform
variable "droplet_id" {
  description = "(required)"
  type        = number
}

variable "ip_address" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_floating_ip_assignment" "this" {
  droplet_id = var.droplet_id
  ip_address = var.ip_address
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_floating_ip_assignment.this.id
}

output "this" {
  value = digitalocean_floating_ip_assignment.this
}
```

[top](#index)