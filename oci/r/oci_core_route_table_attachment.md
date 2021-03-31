# oci_core_route_table_attachment

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_route_table_attachment" {
  source = "./modules/oci/r/oci_core_route_table_attachment"

  # route_table_id - (required) is a type of string
  route_table_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null

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
variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
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
resource "oci_core_route_table_attachment" "this" {
  route_table_id = var.route_table_id
  subnet_id      = var.subnet_id

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
  value       = oci_core_route_table_attachment.this.id
}

output "this" {
  value = oci_core_route_table_attachment.this
}
```

[top](#index)