# digitalocean_container_registry_docker_credentials

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
module "digitalocean_container_registry_docker_credentials" {
  source = "./modules/digitalocean/r/digitalocean_container_registry_docker_credentials"

  # expiry_seconds - (optional) is a type of number
  expiry_seconds = null
  # registry_name - (required) is a type of string
  registry_name = null
  # write - (optional) is a type of bool
  write = null
}
```

[top](#index)

### Variables

```terraform
variable "expiry_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "registry_name" {
  description = "(required)"
  type        = string
}

variable "write" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_container_registry_docker_credentials" "this" {
  expiry_seconds = var.expiry_seconds
  registry_name  = var.registry_name
  write          = var.write
}
```

[top](#index)

### Outputs

```terraform
output "credential_expiration_time" {
  description = "returns a string"
  value       = digitalocean_container_registry_docker_credentials.this.credential_expiration_time
}

output "docker_credentials" {
  description = "returns a string"
  value       = digitalocean_container_registry_docker_credentials.this.docker_credentials
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = digitalocean_container_registry_docker_credentials.this.id
}

output "this" {
  value = digitalocean_container_registry_docker_credentials.this
}
```

[top](#index)