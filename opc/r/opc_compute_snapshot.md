# opc_compute_snapshot

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_snapshot" {
  source = "./modules/opc/r/opc_compute_snapshot"

  # account - (optional) is a type of string
  account = null
  # instance - (required) is a type of string
  instance = null
  # machine_image - (optional) is a type of string
  machine_image = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance" {
  description = "(required)"
  type        = string
}

variable "machine_image" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_snapshot" "this" {
  # account - (optional) is a type of string
  account = var.account
  # instance - (required) is a type of string
  instance = var.instance
  # machine_image - (optional) is a type of string
  machine_image = var.machine_image

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
  value       = opc_compute_snapshot.this.account
}

output "creation_time" {
  description = "returns a string"
  value       = opc_compute_snapshot.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = opc_compute_snapshot.this.id
}

output "machine_image" {
  description = "returns a string"
  value       = opc_compute_snapshot.this.machine_image
}

output "name" {
  description = "returns a string"
  value       = opc_compute_snapshot.this.name
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_snapshot.this.uri
}

output "this" {
  value = opc_compute_snapshot.this
}
```

[top](#index)