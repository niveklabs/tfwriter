# vault_rabbitmq_secret_backend_role

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
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_rabbitmq_secret_backend_role" {
  source = "./modules/vault/r/vault_rabbitmq_secret_backend_role"

  # backend - (required) is a type of string
  backend = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of string
  tags = null

  vhost = [{
    configure = null
    host      = null
    read      = null
    write     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The path of the Rabbitmq Secret Backend the role belongs to."
  type        = string
}

variable "name" {
  description = "(required) - Unique name for the role."
  type        = string
}

variable "tags" {
  description = "(optional) - Specifies a comma-separated RabbitMQ management tags."
  type        = string
  default     = null
}

variable "vhost" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      configure = string
      host      = string
      read      = string
      write     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vault_rabbitmq_secret_backend_role" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of string
  tags = var.tags

  dynamic "vhost" {
    for_each = var.vhost
    content {
      # configure - (required) is a type of string
      configure = vhost.value["configure"]
      # host - (required) is a type of string
      host = vhost.value["host"]
      # read - (required) is a type of string
      read = vhost.value["read"]
      # write - (required) is a type of string
      write = vhost.value["write"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_rabbitmq_secret_backend_role.this.id
}

output "this" {
  value = vault_rabbitmq_secret_backend_role.this
}
```

[top](#index)