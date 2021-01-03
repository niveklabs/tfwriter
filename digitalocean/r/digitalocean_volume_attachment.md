# digitalocean_volume_attachment

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
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_volume_attachment" {
  source = "./modules/digitalocean/r/digitalocean_volume_attachment"

  # droplet_id - (required) is a type of number
  droplet_id = null
  # volume_id - (required) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "droplet_id" {
  description = "(required)"
  type        = number
}

variable "volume_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_volume_attachment" "this" {
  droplet_id = var.droplet_id
  volume_id  = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_volume_attachment.this.id
}

output "this" {
  value = digitalocean_volume_attachment.this
}
```

[top](#index)