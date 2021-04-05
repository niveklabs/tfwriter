# okta_inline_hook

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_inline_hook" {
  source = "./modules/okta/r/okta_inline_hook"

  # auth - (optional) is a type of map of string
  auth = {}
  # channel - (required) is a type of map of string
  channel = {}
  # name - (required) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
  # type - (required) is a type of string
  type = null
  # version - (required) is a type of string
  version = null

  headers = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "channel" {
  description = "(required)"
  type        = map(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "headers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_inline_hook" "this" {
  auth    = var.auth
  channel = var.channel
  name    = var.name
  status  = var.status
  type    = var.type
  version = var.version

  dynamic "headers" {
    for_each = var.headers
    content {
      key   = headers.value["key"]
      value = headers.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_inline_hook.this.id
}

output "this" {
  value = okta_inline_hook.this
}
```

[top](#index)