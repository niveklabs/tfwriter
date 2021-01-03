# opc_compute_storage_attachment

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
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_storage_attachment" {
  source = "./modules/opc/r/opc_compute_storage_attachment"

  # index - (required) is a type of number
  index = null
  # instance - (required) is a type of string
  instance = null
  # storage_volume - (required) is a type of string
  storage_volume = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "index" {
  description = "(required)"
  type        = number
}

variable "instance" {
  description = "(required)"
  type        = string
}

variable "storage_volume" {
  description = "(required)"
  type        = string
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
resource "opc_compute_storage_attachment" "this" {
  index          = var.index
  instance       = var.instance
  storage_volume = var.storage_volume

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_storage_attachment.this.id
}

output "this" {
  value = opc_compute_storage_attachment.this
}
```

[top](#index)