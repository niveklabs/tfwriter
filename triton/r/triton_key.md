# triton_key

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_key" {
  source = "./modules/triton/r/triton_key"

  # key - (required) is a type of string
  key = null
  # name - (optional) is a type of string
  name = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required) - Content of public key from disk in OpenSSH format"
  type        = string
}

variable "name" {
  description = "(optional) - Name of the key (generated from the key comment if not set)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "triton_key" "this" {
  # key - (required) is a type of string
  key = var.key
  # name - (optional) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = triton_key.this.id
}

output "name" {
  description = "returns a string"
  value       = triton_key.this.name
}

output "this" {
  value = triton_key.this
}
```

[top](#index)