# brightbox_api_client

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_api_client" {
  source = "./modules/brightbox/r/brightbox_api_client"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # permissions_group - (optional) is a type of string
  permissions_group = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Verbose Description of this client"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Human Readable Name"
  type        = string
  default     = null
}

variable "permissions_group" {
  description = "(optional) - Summary of the permissions granted to the client (full, storage)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_api_client" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # permissions_group - (optional) is a type of string
  permissions_group = var.permissions_group

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account" {
  description = "returns a string"
  value       = brightbox_api_client.this.account
}

output "id" {
  description = "returns a string"
  value       = brightbox_api_client.this.id
}

output "secret" {
  description = "returns a string"
  value       = brightbox_api_client.this.secret
  sensitive   = true
}

output "this" {
  value = brightbox_api_client.this
}
```

[top](#index)