# digitalocean_account

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
module "digitalocean_account" {
  source = "./modules/digitalocean/d/digitalocean_account"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "digitalocean_account" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "droplet_limit" {
  description = "returns a number"
  value       = data.digitalocean_account.this.droplet_limit
}

output "email" {
  description = "returns a string"
  value       = data.digitalocean_account.this.email
}

output "email_verified" {
  description = "returns a bool"
  value       = data.digitalocean_account.this.email_verified
}

output "floating_ip_limit" {
  description = "returns a number"
  value       = data.digitalocean_account.this.floating_ip_limit
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_account.this.id
}

output "status" {
  description = "returns a string"
  value       = data.digitalocean_account.this.status
}

output "status_message" {
  description = "returns a string"
  value       = data.digitalocean_account.this.status_message
}

output "uuid" {
  description = "returns a string"
  value       = data.digitalocean_account.this.uuid
}

output "this" {
  value = digitalocean_account.this
}
```

[top](#index)