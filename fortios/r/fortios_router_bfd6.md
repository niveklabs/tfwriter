# fortios_router_bfd6

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
module "fortios_router_bfd6" {
  source = "./modules/fortios/r/fortios_router_bfd6"


  neighbor = [{
    interface   = null
    ip6_address = null
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
      interface   = string
      ip6_address = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_bfd6" "this" {

  dynamic "neighbor" {
    for_each = var.neighbor
    content {
      interface   = neighbor.value["interface"]
      ip6_address = neighbor.value["ip6_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_bfd6.this.id
}

output "this" {
  value = fortios_router_bfd6.this
}
```

[top](#index)