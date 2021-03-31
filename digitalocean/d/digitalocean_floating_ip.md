# digitalocean_floating_ip

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/digitalocean/d/digitalocean_floating_ip"

  # ip_address - (required) is a type of string
  ip_address = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_address" {
  description = "(required) - floating ip address"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_floating_ip" "this" {
  ip_address = var.ip_address
}
```

[top](#index)

### Outputs

```terraform
output "droplet_id" {
  description = "returns a number"
  value       = data.digitalocean_floating_ip.this.droplet_id
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_floating_ip.this.id
}

output "region" {
  description = "returns a string"
  value       = data.digitalocean_floating_ip.this.region
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_floating_ip.this.urn
}

output "this" {
  value = digitalocean_floating_ip.this
}
```

[top](#index)