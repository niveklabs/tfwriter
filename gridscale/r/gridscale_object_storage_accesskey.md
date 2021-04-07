# gridscale_object_storage_accesskey

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
module "gridscale_object_storage_accesskey" {
  source = "./modules/gridscale/r/gridscale_object_storage_accesskey"


  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
resource "gridscale_object_storage_accesskey" "this" {

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
output "access_key" {
  description = "returns a string"
  value       = gridscale_object_storage_accesskey.this.access_key
}

output "id" {
  description = "returns a string"
  value       = gridscale_object_storage_accesskey.this.id
}

output "secret_key" {
  description = "returns a string"
  value       = gridscale_object_storage_accesskey.this.secret_key
}

output "this" {
  value = gridscale_object_storage_accesskey.this
}
```

[top](#index)