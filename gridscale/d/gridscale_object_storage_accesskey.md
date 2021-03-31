# gridscale_object_storage_accesskey

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/gridscale/d/gridscale_object_storage_accesskey"

  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_object_storage_accesskey" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "access_key" {
  description = "returns a string"
  value       = data.gridscale_object_storage_accesskey.this.access_key
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_object_storage_accesskey.this.id
}

output "secret_key" {
  description = "returns a string"
  value       = data.gridscale_object_storage_accesskey.this.secret_key
}

output "this" {
  value = gridscale_object_storage_accesskey.this
}
```

[top](#index)