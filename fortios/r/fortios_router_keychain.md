# fortios_router_keychain

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_router_keychain" {
  source = "./modules/fortios/r/fortios_router_keychain"

  # name - (required) is a type of string
  name = null

  key = [{
    accept_lifetime = null
    id              = null
    key_string      = null
    send_lifetime   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "key" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      accept_lifetime = string
      id              = number
      key_string      = string
      send_lifetime   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_keychain" "this" {
  name = var.name

  dynamic "key" {
    for_each = var.key
    content {
      accept_lifetime = key.value["accept_lifetime"]
      id              = key.value["id"]
      key_string      = key.value["key_string"]
      send_lifetime   = key.value["send_lifetime"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_keychain.this.id
}

output "this" {
  value = fortios_router_keychain.this
}
```

[top](#index)