# oci_load_balancer_ssl_cipher_suite

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_ssl_cipher_suite" {
  source = "./modules/oci/r/oci_load_balancer_ssl_cipher_suite"

  # ciphers - (required) is a type of list of string
  ciphers = []
  # load_balancer_id - (optional) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ciphers" {
  description = "(required)"
  type        = list(string)
}

variable "load_balancer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_load_balancer_ssl_cipher_suite" "this" {
  # ciphers - (required) is a type of list of string
  ciphers = var.ciphers
  # load_balancer_id - (optional) is a type of string
  load_balancer_id = var.load_balancer_id
  # name - (required) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
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
  value       = oci_load_balancer_ssl_cipher_suite.this.id
}

output "load_balancer_id" {
  description = "returns a string"
  value       = oci_load_balancer_ssl_cipher_suite.this.load_balancer_id
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_ssl_cipher_suite.this.state
}

output "this" {
  value = oci_load_balancer_ssl_cipher_suite.this
}
```

[top](#index)