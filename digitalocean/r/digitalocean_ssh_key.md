# digitalocean_ssh_key

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
module "digitalocean_ssh_key" {
  source = "./modules/digitalocean/r/digitalocean_ssh_key"

  # name - (required) is a type of string
  name = null
  # public_key - (required) is a type of string
  public_key = null
}
```

[top](#index)

### Variables

```terraform
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
resource "digitalocean_ssh_key" "this" {
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
  value       = digitalocean_ssh_key.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = digitalocean_ssh_key.this.id
}

output "this" {
  value = digitalocean_ssh_key.this
}
```

[top](#index)