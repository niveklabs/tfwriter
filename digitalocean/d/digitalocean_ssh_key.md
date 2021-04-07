# digitalocean_ssh_key

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
module "digitalocean_ssh_key" {
  source = "./modules/digitalocean/d/digitalocean_ssh_key"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of the ssh key"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_ssh_key" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = data.digitalocean_ssh_key.this.fingerprint
}

output "id" {
  description = "returns a number"
  value       = data.digitalocean_ssh_key.this.id
}

output "public_key" {
  description = "returns a string"
  value       = data.digitalocean_ssh_key.this.public_key
}

output "this" {
  value = digitalocean_ssh_key.this
}
```

[top](#index)