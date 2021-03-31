# gridscale_sshkey

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_sshkey" {
  source = "./modules/gridscale/r/gridscale_sshkey"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # sshkey - (required) is a type of string
  sshkey = null

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
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters."
  type        = string
}

variable "sshkey" {
  description = "(required) - sshkey_string is the OpenSSH public key string (all key types are supported => ed25519, ecdsa, dsa, rsa, rsa1)"
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
resource "gridscale_sshkey" "this" {
  labels = var.labels
  name   = var.name
  sshkey = var.sshkey

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = gridscale_sshkey.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_sshkey.this.create_time
}

output "id" {
  description = "returns a string"
  value       = gridscale_sshkey.this.id
}

output "status" {
  description = "returns a string"
  value       = gridscale_sshkey.this.status
}

output "this" {
  value = gridscale_sshkey.this
}
```

[top](#index)