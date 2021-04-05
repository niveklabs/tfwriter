# skytap_icnr_tunnel

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_icnr_tunnel" {
  source = null

  # source - (required) is a type of number
  # target - (required) is a type of number
  target = null

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
variable "source" {
  description = "(required)"
  type        = number
}

variable "target" {
  description = "(required)"
  type        = number
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
resource "skytap_icnr_tunnel" "this" {
  source = var.source
  target = var.target

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
output "id" {
  description = "returns a string"
  value       = skytap_icnr_tunnel.this.id
}

output "this" {
  value = skytap_icnr_tunnel.this
}
```

[top](#index)