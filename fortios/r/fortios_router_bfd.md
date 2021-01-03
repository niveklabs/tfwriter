# fortios_router_bfd

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
module "fortios_router_bfd" {
  source = "./modules/fortios/r/fortios_router_bfd"


  neighbor = [{
    interface = null
    ip        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "neighbor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface = string
      ip        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_bfd" "this" {

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      interface = neighbor.value["interface"]
      ip        = neighbor.value["ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_bfd.this.id
}

output "this" {
  value = fortios_router_bfd.this
}
```

[top](#index)