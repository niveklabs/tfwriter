# digitalocean_floating_ip

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
module "digitalocean_floating_ip" {
  source = "./modules/digitalocean/r/digitalocean_floating_ip"

  # droplet_id - (optional) is a type of number
  droplet_id = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "droplet_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_floating_ip" "this" {
  # droplet_id - (optional) is a type of number
  droplet_id = var.droplet_id
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # region - (required) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_floating_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = digitalocean_floating_ip.this.ip_address
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_floating_ip.this.urn
}

output "this" {
  value = digitalocean_floating_ip.this
}
```

[top](#index)