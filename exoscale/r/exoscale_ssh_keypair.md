# exoscale_ssh_keypair

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_ssh_keypair" {
  source = "./modules/exoscale/r/exoscale_ssh_keypair"

  # name - (required) is a type of string
  name = null
  # public_key - (optional) is a type of string
  public_key = null

  timeouts = [{
    create = null
    delete = null
    read   = null
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

variable "public_key" {
  description = "(optional)"
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_ssh_keypair" "this" {
  # name - (required) is a type of string
  name = var.name
  # public_key - (optional) is a type of string
  public_key = var.public_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = exoscale_ssh_keypair.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = exoscale_ssh_keypair.this.id
}

output "private_key" {
  description = "returns a string"
  value       = exoscale_ssh_keypair.this.private_key
  sensitive   = true
}

output "this" {
  value = exoscale_ssh_keypair.this
}
```

[top](#index)