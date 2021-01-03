# vault_rabbitmq_secret_backend

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_rabbitmq_secret_backend" {
  source = "./modules/vault/r/vault_rabbitmq_secret_backend"

  # connection_uri - (required) is a type of string
  connection_uri = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # password - (required) is a type of string
  password = null
  # path - (optional) is a type of string
  path = null
  # username - (required) is a type of string
  username = null
  # verify_connection - (optional) is a type of bool
  verify_connection = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_uri" {
  description = "(required) - Specifies the RabbitMQ connection URI."
  type        = string
}

variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "password" {
  description = "(required) - Specifies the RabbitMQ management administrator password"
  type        = string
}

variable "path" {
  description = "(optional) - The path of the RabbitMQ Secret Backend where the connection should be configured"
  type        = string
  default     = null
}

variable "username" {
  description = "(required) - Specifies the RabbitMQ management administrator username"
  type        = string
}

variable "verify_connection" {
  description = "(optional) - Specifies whether to verify connection URI, username, and password."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_rabbitmq_secret_backend" "this" {
  connection_uri            = var.connection_uri
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  description               = var.description
  max_lease_ttl_seconds     = var.max_lease_ttl_seconds
  password                  = var.password
  path                      = var.path
  username                  = var.username
  verify_connection         = var.verify_connection
}
```

[top](#index)

### Outputs

```terraform
output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_rabbitmq_secret_backend.this.default_lease_ttl_seconds
}

output "id" {
  description = "returns a string"
  value       = vault_rabbitmq_secret_backend.this.id
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_rabbitmq_secret_backend.this.max_lease_ttl_seconds
}

output "this" {
  value = vault_rabbitmq_secret_backend.this
}
```

[top](#index)