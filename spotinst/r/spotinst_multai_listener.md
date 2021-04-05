# spotinst_multai_listener

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_multai_listener" {
  source = "./modules/spotinst/r/spotinst_multai_listener"

  # balancer_id - (required) is a type of string
  balancer_id = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null

  tags = [{
    key   = null
    value = null
  }]

  tls_config = [{
    certificate_ids             = []
    cipher_suites               = []
    max_version                 = null
    min_version                 = null
    prefer_server_cipher_suites = null
    session_tickets_disabled    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "balancer_id" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "tls_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_ids             = list(string)
      cipher_suites               = list(string)
      max_version                 = string
      min_version                 = string
      prefer_server_cipher_suites = bool
      session_tickets_disabled    = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_multai_listener" "this" {
  balancer_id = var.balancer_id
  port        = var.port
  protocol    = var.protocol

  dynamic "tags" {
    for_each = var.tags
    content {
      key   = tags.value["key"]
      value = tags.value["value"]
    }
  }

  dynamic "tls_config" {
    for_each = var.tls_config
    content {
      certificate_ids             = tls_config.value["certificate_ids"]
      cipher_suites               = tls_config.value["cipher_suites"]
      max_version                 = tls_config.value["max_version"]
      min_version                 = tls_config.value["min_version"]
      prefer_server_cipher_suites = tls_config.value["prefer_server_cipher_suites"]
      session_tickets_disabled    = tls_config.value["session_tickets_disabled"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_multai_listener.this.id
}

output "this" {
  value = spotinst_multai_listener.this
}
```

[top](#index)